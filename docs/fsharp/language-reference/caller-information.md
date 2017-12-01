---
title: "Сведения о вызывающем объекте (F #)"
description: "Описывает, как использовать информационные атрибуты аргумент вызывающего, чтобы получить сведения о вызывающем объекте из метода."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 04/25/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a3dcc335-433b-4672-ac2d-ae6b11b816f3
ms.openlocfilehash: 533d2f0429ddb31e6d1dd7efca2f0760069a2945
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="caller-information"></a>Сведения о вызывающем объекте

С помощью информационных атрибутов вызывающего объекта можно получить сведения о вызывающем объекте метода. Можно получить путь к файлу исходного кода, номер строки в исходном коде и имя вызывающего объекта. Эти сведения полезны для трассировки, отладки и создания средств диагностики.

Для получения этих сведений используются атрибуты, которые применяются к необязательным параметрам, каждый из которых имеет значение по умолчанию. В следующей таблице перечислены информационные атрибуты вызывающего объекта, определенные в [System.Runtime.CompilerServices](/dotnet/api/system.runtime.compilerservices) пространство имен:

|Атрибут|Описание|Тип|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Полный путь исходного файла, содержащего вызывающий объект. Это путь к файлу во время компиляции.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Номер строки в исходном файле, в которой вызывается метод.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Имя свойства или метода вызывающего объекта. В разделе имена членов далее в этом разделе.|`String`|

## <a name="example"></a>Пример

Следующий пример показывает, как эти атрибуты можно использовать для трассировки вызывающий объект.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices

type Tracer() =
    member __.DoTrace(msg: string,
                      [<CallerMemberName>] ?memberName: string,
                      [<CallerFilePath>] ?path: string
                      [<CallerLineNumber>] ?line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        match (memberName, path, line) with
        | Some m, Some p, Some l ->
            Trace.WriteLine(sprintf "Member name: %s" m)
            Trace.WriteLine(sprintf "Source file path: %s" p)
            Trace.WriteLine(sprintf "Source line number: %d" l)
        | _,_,_ -> ()
```

## <a name="remarks"></a>Примечания

Информационные атрибуты вызывающего может применяться только к необязательным параметрам. Необходимо указать явное значение для каждого необязательного параметра. Информационные атрибуты вызывающего объекта привести к записи правильное значение для каждого необязательного параметра, помеченной атрибутом информация вызывающего объекта.

Информационные значения вызывающего объекта передаются как литералы в IL во время компиляции. В отличие от результатов [StackTrace](/dotnet/api/system.diagnostics.stacktrace) свойство для исключений, результаты не затрагиваются запутыванием кода.

Можно явно передать необязательные аргументы, чтобы управлять сведениями о вызывающем объекте или скрывать сведения о вызывающем объекте.

## <a name="member-names"></a>Имена элементов

Можно использовать [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, чтобы не указывать имя члена в виде `String` аргументов для вызываемого метода. При использовании этого метода позволяет избежать проблемы, не меняется, рефакторинга и переименования `String` значения. Это особенно полезно при выполнении следующих задач:

* Использование процедур трассировки и диагностики.
* Реализация [INotifyPropertyChanged](/dotnet/api/system.componentmodel.inotifypropertychanged) интерфейс при привязке данных. Этот интерфейс позволяет свойству объекта уведомлять связанный элемент управления об изменении свойства, чтобы элемент управления мог отображать обновленные сведения. Без [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) атрибут, необходимо указать имя свойства как литерал.

Следующая диаграмма показывает элемент имена, которые возвращаются при использовании атрибут CallerMemberName.

|Фрагмент кода, в пределах которого происходит вызов|Результат имени члена|
|-------------------|------------------|
|Метод, свойство или событие|Имя метода, свойства или события, из которого происходил вызов.|
|Конструктор|Строка ".ctor"|
|Статический конструктор|Строка ".cctor"|
|Деструктор|Строка "Finalize"|
|Определяемые пользователем операторы и преобразования|Созданное имя члена, например, "op_Addition".|
|Конструктора атрибута|Имя члена, к которому применяется атрибут. Если атрибут — любой элемент внутри члена (например, параметр, возвращаемое значение или параметр универсального типа), то результат — имя члена, который связан с этим элементом.|
|Нет содержащего члена (например, уровень сборки или атрибуты, примененные к типам)|Значение необязательного параметра по умолчанию.|

## <a name="see-also"></a>См. также
 [Атрибуты](attributes.md)  
 [Именованные аргументы](parameters-and-arguments.md#named-arguments)  
 [Необязательные параметры](parameters-and-arguments.md#optional-parameters)  