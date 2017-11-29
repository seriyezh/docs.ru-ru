---
title: "Кортежи в Visual Basic"
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be50b22e9acca9ff8cfbde798d78869ee1c72634
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="tuples-visual-basic"></a><span data-ttu-id="dee23-102">Кортежи (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dee23-102">Tuples (Visual Basic)</span></span>

<span data-ttu-id="dee23-103">Начиная с Visual Basic 2017 г., в языке Visual Basic предлагает встроенную поддержку кортежей, который делает создание кортежей и доступ к элементам проще кортежей.</span><span class="sxs-lookup"><span data-stu-id="dee23-103">Starting with Visual Basic 2017, the Visual Basic language offers built-in support for tuples that makes creating tuples and accessing the elements of tuples easier.</span></span> <span data-ttu-id="dee23-104">Кортеж — это структура данных недоступно, с определенным номером и последовательность значений.</span><span class="sxs-lookup"><span data-stu-id="dee23-104">A tuple is a light-weight data structure that has a specific number and sequence of values.</span></span> <span data-ttu-id="dee23-105">При создании экземпляра кортежа, следует определить, количество и тип данных каждого значения (или элемент).</span><span class="sxs-lookup"><span data-stu-id="dee23-105">When you instantiate the tuple, you define the number and the data type of each value (or element).</span></span> <span data-ttu-id="dee23-106">Например кортеж (или пары) состоит из двух элементов.</span><span class="sxs-lookup"><span data-stu-id="dee23-106">For example, a 2-tuple (or pair) has two elements.</span></span> <span data-ttu-id="dee23-107">Возможно, первый `Boolean` значение, а второй — `String`.</span><span class="sxs-lookup"><span data-stu-id="dee23-107">The first might be a `Boolean` value, while the second is a `String`.</span></span> <span data-ttu-id="dee23-108">Поскольку кортежей упростить процесс сохранения нескольких значений в одном объекте, они часто используются как упрощенный способ возвращать несколько значений из метода.</span><span class="sxs-lookup"><span data-stu-id="dee23-108">Because tuples make it easy to store multiple values in a single object, they are often used as a lightweight way to return multiple values from a method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dee23-109">Поддержка кортежа требует <xref:System.ValueTuple> типа.</span><span class="sxs-lookup"><span data-stu-id="dee23-109">Tuple support requires the <xref:System.ValueTuple> type.</span></span> <span data-ttu-id="dee23-110">Если 4.7 .NET Framework не установлена, необходимо добавить пакет NuGet `System.ValueTuple`, который можно найти в коллекции NuGet.</span><span class="sxs-lookup"><span data-stu-id="dee23-110">If the .NET Framework 4.7 is not installed, you must add the NuGet package `System.ValueTuple`, which is available on the NuGet Gallery.</span></span> <span data-ttu-id="dee23-111">Без этого пакета может получить ошибку компиляции аналогично «Предопределенный тип «ValueTuple(Of,,,)» не определен и не импортирован.»</span><span class="sxs-lookup"><span data-stu-id="dee23-111">Without this package, you may get a compilation error similar to, "Predefined type 'ValueTuple(Of,,,)' is not defined or imported."</span></span>

## <a name="instantiating-and-using-a-tuple"></a><span data-ttu-id="dee23-112">Создание и использование кортежа</span><span class="sxs-lookup"><span data-stu-id="dee23-112">Instantiating and using a tuple</span></span>

<span data-ttu-id="dee23-113">Создать кортеж, заключив его круглые скобки обмена мгновенными сообщениями значений с разделителями запятыми.</span><span class="sxs-lookup"><span data-stu-id="dee23-113">You instantiate a tuple by enclosing its comma-delimited values im parentheses.</span></span> <span data-ttu-id="dee23-114">Затем каждый из этих значений становится полем кортежа.</span><span class="sxs-lookup"><span data-stu-id="dee23-114">Each of those values then becomes a field of the tuple.</span></span> <span data-ttu-id="dee23-115">Например, следующий код определяет triple (или кортежа 3) с помощью `Date` как значение его первого, `String` его вторым и `Boolean` как третьего.</span><span class="sxs-lookup"><span data-stu-id="dee23-115">For example, the following code defines a triple (or 3-tuple) with a `Date` as its first value, a `String` as its second, and a `Boolean` as its third.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

<span data-ttu-id="dee23-116">По умолчанию имя каждого поля в кортеж включает строку `Item` вместе с положением на основе одного поля в кортеже.</span><span class="sxs-lookup"><span data-stu-id="dee23-116">By default, the name of each field in a tuple consists of the string `Item` along with the field's one-based position in the tuple.</span></span> <span data-ttu-id="dee23-117">Для 3-кортежа `Date` поле является `Item1`, `String` поле является `Item2`и `Boolean` поле является `Item3`.</span><span class="sxs-lookup"><span data-stu-id="dee23-117">For this 3-tuple, the `Date` field is `Item1`, the `String` field is `Item2`, and the `Boolean` field is `Item3`.</span></span> <span data-ttu-id="dee23-118">Следующий пример отображает значения полей кортежа, созданный в предыдущей строке кода</span><span class="sxs-lookup"><span data-stu-id="dee23-118">The following example displays the values of fields of the tuple instantiated in the previous line of code</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

<span data-ttu-id="dee23-119">Поля кортеж Visual Basic, чтения и записи; После создания экземпляра кортеж его значения можно изменить.</span><span class="sxs-lookup"><span data-stu-id="dee23-119">The fields of a Visual Basic tuple are read-write; after you've instantiated a tuple, you can modify its values.</span></span> <span data-ttu-id="dee23-120">Следующий пример изменяет две из трех полей кортежа, созданные в предыдущем примере и отображает результат.</span><span class="sxs-lookup"><span data-stu-id="dee23-120">The following example modifies two of the three fields of the tuple created in the previous example and displays the result.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a><span data-ttu-id="dee23-121">Создание экземпляра и использование именованных кортежа</span><span class="sxs-lookup"><span data-stu-id="dee23-121">Instantiating and using a named tuple</span></span>

<span data-ttu-id="dee23-122">Вместо того чтобы использовать имена по умолчанию для полей кортежа, можно создать экземпляр *кортеж с именем* , назначив собственные имена элементов кортежа.</span><span class="sxs-lookup"><span data-stu-id="dee23-122">Rather than using default names for a tuple's fields, you can instantiate a *named tuple* by assigning your own names to the tuple's elements.</span></span> <span data-ttu-id="dee23-123">Поля кортежа может осуществляться по именам и назначенный *или* , их имена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dee23-123">The tuple's fields can then be accessed by their assigned names *or* by their default names.</span></span> <span data-ttu-id="dee23-124">В следующем примере создается же кортеж 3 как ранее, за исключением того, что она явно указана первое поле `EventDate`, второй `Name`, а в третьем `IsHoliday`.</span><span class="sxs-lookup"><span data-stu-id="dee23-124">The following example instantiates the same 3-tuple as previously, except that it explicitly names the first field `EventDate`, the second `Name`, and the third `IsHoliday`.</span></span> <span data-ttu-id="dee23-125">Затем он отображает значения полей, изменяет их и отображает значения полей еще раз.</span><span class="sxs-lookup"><span data-stu-id="dee23-125">It then displays the field values, modifies them, and displays the field values again.</span></span>

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="tuples-versus-structures"></a><span data-ttu-id="dee23-126">Кортежи и структур</span><span class="sxs-lookup"><span data-stu-id="dee23-126">Tuples versus structures</span></span>

<span data-ttu-id="dee23-127">Кортеж Visual Basic — это тип значения, который представляет собой экземпляр одного из **System.ValueTuple** универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="dee23-127">A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types.</span></span> <span data-ttu-id="dee23-128">Например `holiday` кортежа, определенных в предыдущем примере является экземпляром класса <xref:System.ValueTuple%603> структуры.</span><span class="sxs-lookup"><span data-stu-id="dee23-128">For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure.</span></span> <span data-ttu-id="dee23-129">Она должна быть упрощенный контейнер для данных.</span><span class="sxs-lookup"><span data-stu-id="dee23-129">It is designed to be a lightweight container for data.</span></span> <span data-ttu-id="dee23-130">Поскольку кортежа стремится упростить процесс создания объекта с несколькими элементами данных, он не имеет некоторые возможности, которые может иметь пользовательскую структуру.</span><span class="sxs-lookup"><span data-stu-id="dee23-130">Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have.</span></span> <span data-ttu-id="dee23-131">К ним относятся следующие методы.</span><span class="sxs-lookup"><span data-stu-id="dee23-131">These include:</span></span>

- <span data-ttu-id="dee23-132">Члены клиента.</span><span class="sxs-lookup"><span data-stu-id="dee23-132">Customer members.</span></span> <span data-ttu-id="dee23-133">Не удается определить собственные свойства, методы или события для кортеж.</span><span class="sxs-lookup"><span data-stu-id="dee23-133">You cannot define your own properties, methods, or events for a tuple.</span></span>

- <span data-ttu-id="dee23-134">Проверка.</span><span class="sxs-lookup"><span data-stu-id="dee23-134">Validation.</span></span> <span data-ttu-id="dee23-135">Не удалось проверить данные, присвоенные поля.</span><span class="sxs-lookup"><span data-stu-id="dee23-135">You cannot validate the data assigned to fields.</span></span>

- <span data-ttu-id="dee23-136">Неизменность.</span><span class="sxs-lookup"><span data-stu-id="dee23-136">Immutability.</span></span> <span data-ttu-id="dee23-137">Кортежи Visual Basic может изменяться.</span><span class="sxs-lookup"><span data-stu-id="dee23-137">Visual Basic tuples are mutable.</span></span> <span data-ttu-id="dee23-138">В отличие от этого пользовательская структура позволяет вам управлять ли экземпляр изменяемым или неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="dee23-138">In contrast, a custom structure allows you to control whether an instance is mutable or immutable.</span></span>

<span data-ttu-id="dee23-139">Если пользовательские элементы, свойства и проверка полей или неизменность важны, следует использовать в Visual Basic [структуры](../../../language-reference/statements/structure-statement.md) инструкцию, чтобы определить тип пользовательского значения.</span><span class="sxs-lookup"><span data-stu-id="dee23-139">If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.</span></span>

<span data-ttu-id="dee23-140">Кортеж Visual Basic наследуют элементы его **ValueTuple** типа.</span><span class="sxs-lookup"><span data-stu-id="dee23-140">A Visual Basic tuple does inherit the members of its **ValueTuple** type.</span></span> <span data-ttu-id="dee23-141">В дополнение к его полям к ним относятся следующие методы:</span><span class="sxs-lookup"><span data-stu-id="dee23-141">In addition to its fields, these include the following methods:</span></span>

| <span data-ttu-id="dee23-142">Член</span><span class="sxs-lookup"><span data-stu-id="dee23-142">Member</span></span> | <span data-ttu-id="dee23-143">Описание</span><span class="sxs-lookup"><span data-stu-id="dee23-143">Description</span></span> |
| ---|---|
| <span data-ttu-id="dee23-144">CompareTo</span><span class="sxs-lookup"><span data-stu-id="dee23-144">CompareTo</span></span> | <span data-ttu-id="dee23-145">Сравнивает текущий кортеж другой кортежу с одинаковым числом элементов.</span><span class="sxs-lookup"><span data-stu-id="dee23-145">Compares the current tuple to another tuple with the same number of elements.</span></span> |
| <span data-ttu-id="dee23-146">Равно</span><span class="sxs-lookup"><span data-stu-id="dee23-146">Equals</span></span> | <span data-ttu-id="dee23-147">Определяет, равен ли текущий кортеж другой кортеж или объектом.</span><span class="sxs-lookup"><span data-stu-id="dee23-147">Determines whether the current tuple is equal to another tuple or object.</span></span> |
| <span data-ttu-id="dee23-148">GetHashCode</span><span class="sxs-lookup"><span data-stu-id="dee23-148">GetHashCode</span></span> | <span data-ttu-id="dee23-149">Вычисляет хэш-код для текущего экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dee23-149">Calculates the hash code for the current instance.</span></span> |
| <span data-ttu-id="dee23-150">ToString</span><span class="sxs-lookup"><span data-stu-id="dee23-150">ToString</span></span> | <span data-ttu-id="dee23-151">Возвращает строковое представление в виде кортежа `(Item1, Item2...)`, где `Item1` и `Item2` представляют значения полей кортежа.</span><span class="sxs-lookup"><span data-stu-id="dee23-151">Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields.</span></span> |

<span data-ttu-id="dee23-152">Кроме того **ValueTuple** типы реализуют <xref:System.Collections.IStructuralComparable> и <xref:System.Collections.IStructuralEquatable> интерфейсы, которые позволяют определить функции сравнения клиента.</span><span class="sxs-lookup"><span data-stu-id="dee23-152">In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.</span></span>

## <a name="assignment-and-tuples"></a><span data-ttu-id="dee23-153">Назначение и кортежи</span><span class="sxs-lookup"><span data-stu-id="dee23-153">Assignment and tuples</span></span>

<span data-ttu-id="dee23-154">Visual Basic поддерживает назначение между типами кортежа, имеющих одинаковое число полей.</span><span class="sxs-lookup"><span data-stu-id="dee23-154">Visual Basic supports assignment between tuple types that have the same number of fields.</span></span> <span data-ttu-id="dee23-155">Можно преобразовать типы полей, если выполняется одно из следующих условий:</span><span class="sxs-lookup"><span data-stu-id="dee23-155">The field types can be converted if one of the following is true:</span></span>

- <span data-ttu-id="dee23-156">Поле источника и целевой, того же типа.</span><span class="sxs-lookup"><span data-stu-id="dee23-156">The source and target field are of the same type.</span></span>

- <span data-ttu-id="dee23-157">Расширяющее (или неявными) преобразование исходного типа в конечный тип определяется.</span><span class="sxs-lookup"><span data-stu-id="dee23-157">A widening (or implicit) conversion of the source type to the target type is defined.</span></span> 

- <span data-ttu-id="dee23-158">`Option Strict`— `On`, и определена, сужающего диапазон значений (или явных) преобразования типа источника к целевому типу.</span><span class="sxs-lookup"><span data-stu-id="dee23-158">`Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined.</span></span> <span data-ttu-id="dee23-159">Это преобразование может создать исключение, если исходное значение выходит за пределы типа целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="dee23-159">This conversion can throw an exception if the source value is outside the range of the target type.</span></span>

<span data-ttu-id="dee23-160">Другие преобразования в контексте назначений не учитываются.</span><span class="sxs-lookup"><span data-stu-id="dee23-160">Other conversions are not considered for assignments.</span></span> <span data-ttu-id="dee23-161">Рассмотрим возможные виды назначений между типами кортежей.</span><span class="sxs-lookup"><span data-stu-id="dee23-161">Let's look at the kinds of assignments that are allowed between tuple types.</span></span>

<span data-ttu-id="dee23-162">В приведенных ниже примерах можно использовать указанные переменные:</span><span class="sxs-lookup"><span data-stu-id="dee23-162">Consider these variables used in the following examples:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

<span data-ttu-id="dee23-163">Первые две переменные `unnamed` и `anonymous`, не имеют имен семантики, указанное для поля.</span><span class="sxs-lookup"><span data-stu-id="dee23-163">The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields.</span></span> <span data-ttu-id="dee23-164">По умолчанию используются соответствующие имена полей `Item1` и `Item2`.</span><span class="sxs-lookup"><span data-stu-id="dee23-164">Their field names are the default `Item1` and `Item2`.</span></span> <span data-ttu-id="dee23-165">Последние два переменные `named` и `differentName` имеют имена полей семантики.</span><span class="sxs-lookup"><span data-stu-id="dee23-165">The last two variables, `named` and `differentName` have semantic field names.</span></span> <span data-ttu-id="dee23-166">Обратите внимание на то, что поля в этих двух кортежах называются по-разному.</span><span class="sxs-lookup"><span data-stu-id="dee23-166">Note that these two tuples have different names for the fields.</span></span>

<span data-ttu-id="dee23-167">Все четыре эти кортежей, имеют одинаковый номер полей (так называемый «арность») и типы эти поля идентичны.</span><span class="sxs-lookup"><span data-stu-id="dee23-167">All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical.</span></span> <span data-ttu-id="dee23-168">Таким образом, все эти назначения работают:</span><span class="sxs-lookup"><span data-stu-id="dee23-168">Therefore, all of these assignments work:</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

<span data-ttu-id="dee23-169">Обратите внимание на то, что имена кортежей не назначаются.</span><span class="sxs-lookup"><span data-stu-id="dee23-169">Notice that the names of the tuples are not assigned.</span></span> <span data-ttu-id="dee23-170">Значения полей назначаются в соответствии с порядком полей в кортеже.</span><span class="sxs-lookup"><span data-stu-id="dee23-170">The values of the fields are assigned following the order of the fields in the tuple.</span></span>

<span data-ttu-id="dee23-171">И, наконец, обратите внимание, что можно назначить `named` кортеж `conversion` кортежа, несмотря на то что в первое поле `named` — `Integer`и в первое поле `conversion` — `Long`.</span><span class="sxs-lookup"><span data-stu-id="dee23-171">Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`.</span></span> <span data-ttu-id="dee23-172">Это назначение завершается успешно, поскольку преобразование `Integer` для `Long` расширяющие преобразования.</span><span class="sxs-lookup"><span data-stu-id="dee23-172">This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.</span></span>

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

<span data-ttu-id="dee23-173">Кортежи с различным количеством поля не может быть назначен:</span><span class="sxs-lookup"><span data-stu-id="dee23-173">Tuples with different numbers of fields are not assignable:</span></span>

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a><span data-ttu-id="dee23-174">Кортежи как возвращаемые значения методов</span><span class="sxs-lookup"><span data-stu-id="dee23-174">Tuples as method return values</span></span>

<span data-ttu-id="dee23-175">Метод может возвращать только одно значение.</span><span class="sxs-lookup"><span data-stu-id="dee23-175">A method can return only a single value.</span></span> <span data-ttu-id="dee23-176">Часто хотя вам бы хотелось вызов метода для возврата нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="dee23-176">Frequently, though, you'd like a method call to return multiple values.</span></span> <span data-ttu-id="dee23-177">Чтобы обойти это ограничение несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="dee23-177">There are several ways to work around this limitation:</span></span>

- <span data-ttu-id="dee23-178">Можно создать пользовательский класс или структуру, свойства или поля представляют значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="dee23-178">You can create a custom class or structure whose properties or fields represent values returned by the method.</span></span> <span data-ttu-id="dee23-179">Таким образом — это решение высокой плотности; необходимо определить пользовательский тип которого предназначен только для извлечения значений из вызова метода.</span><span class="sxs-lookup"><span data-stu-id="dee23-179">Thus is a heavyweight solution; it requires that you define a custom type whose only purpose is to retrieve values from a method call.</span></span>

- <span data-ttu-id="dee23-180">Возвращает одно значение из метода и возврата оставшиеся значения, передавая их по ссылке в метод.</span><span class="sxs-lookup"><span data-stu-id="dee23-180">You can return a single value from the method, and return the remaining values by passing them by reference to the method.</span></span> <span data-ttu-id="dee23-181">Это включает в себя дополнительную нагрузку, связанную с создания экземпляра переменной и риски при перезаписи значение переменной, которая передается по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dee23-181">This involves the overhead of instantiating a variable and risks inadvertently overwriting the value of the variable that you pass by reference.</span></span>

- <span data-ttu-id="dee23-182">Можно использовать кортеж, который предоставляет простое решение для извлечения с несколькими возвращаемыми значениями.</span><span class="sxs-lookup"><span data-stu-id="dee23-182">You can use a tuple, which provides a lightweight solution to retrieving multiple return values.</span></span>

<span data-ttu-id="dee23-183">Например **TryParse** методы возврата .NET `Boolean` значение, указывающее, успешно ли выполнена операция синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="dee23-183">For example, the **TryParse** methods in .NET return a `Boolean` value that indicates whether the parsing operation succeeded.</span></span> <span data-ttu-id="dee23-184">Результат операции анализа возвращается в переменную, передаваемый по ссылке в метод.</span><span class="sxs-lookup"><span data-stu-id="dee23-184">The result of the parsing operation is returned in a variable passed by reference to the method.</span></span> <span data-ttu-id="dee23-185">Как правило, вызов метода анализа, такие как <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dee23-185">Normally, a call to the a parsing method such as <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> looks like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

<span data-ttu-id="dee23-186">Мы можем вернуться кортеж из операции анализа, если мы программу-оболочку вызова <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> в нашей методе.</span><span class="sxs-lookup"><span data-stu-id="dee23-186">We can return a tuple from the parsing operation if we wrap the call to the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method in our own method.</span></span> <span data-ttu-id="dee23-187">В следующем примере `NumericLibrary.ParseInteger` вызовы <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> метод и возвращает кортеж, именованный с двумя элементами.</span><span class="sxs-lookup"><span data-stu-id="dee23-187">In the following example, `NumericLibrary.ParseInteger` calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method and returns a named tuple with two elements.</span></span> 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

<span data-ttu-id="dee23-188">Затем можно вызвать метод с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="dee23-188">You can then call the method with code like the following:</span></span>

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a><span data-ttu-id="dee23-189">Visual Basic кортежи и кортежи в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dee23-189">Visual Basic tuples and tuples in the .NET Framework</span></span>

<span data-ttu-id="dee23-190">Visual Basic кортеж представляет собой экземпляр одного из **System.ValueTuple** универсальных типов, которые впервые появились в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="dee23-190">A Visual Basic tuple is an instance of one of the **System.ValueTuple** generic types, which were introduced in the .NET Framework 4.7.</span></span> <span data-ttu-id="dee23-191">Платформа .NET Framework также включает набор универсального **System.Tuple** классы.</span><span class="sxs-lookup"><span data-stu-id="dee23-191">The .NET Framework also includes a set of generic **System.Tuple** classes.</span></span> <span data-ttu-id="dee23-192">Эти классы тем не менее, отличаются от кортежей Visual Basic и **System.ValueTuple** универсальных типов в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="dee23-192">These classes, however, differ from Visual Basic tuples and the **System.ValueTuple** generic types in a number of ways:</span></span>

- <span data-ttu-id="dee23-193">Элементы **кортежа** классы являются свойства с именем `Item1`, `Item2`, и т. д.</span><span class="sxs-lookup"><span data-stu-id="dee23-193">The elements of the **Tuple** classes are properties named `Item1`, `Item2`, and so on.</span></span> <span data-ttu-id="dee23-194">В Visual Basic кортежей и **ValueTuple** поля, типы элементов кортежа.</span><span class="sxs-lookup"><span data-stu-id="dee23-194">In Visual Basic tuples and the **ValueTuple** types, tuple elements are fields.</span></span>

- <span data-ttu-id="dee23-195">Элементы нельзя назначить значимые имена **кортежа** экземпляра или **ValueTuple** экземпляра.</span><span class="sxs-lookup"><span data-stu-id="dee23-195">You cannot assign meaningful names to the elements of a **Tuple** instance or of a **ValueTuple** instance.</span></span> <span data-ttu-id="dee23-196">Visual Basic позволяет присваивать имена, которые смысловое значение поля.</span><span class="sxs-lookup"><span data-stu-id="dee23-196">Visual Basic allows you to assign names that communicate the meaning of the fields.</span></span>

- <span data-ttu-id="dee23-197">Свойства **кортежа** экземпляра доступны только для чтения; кортежи являются неизменяемыми.</span><span class="sxs-lookup"><span data-stu-id="dee23-197">The properties of a **Tuple** instance are read-only; the tuples are immutable.</span></span> <span data-ttu-id="dee23-198">В Visual Basic кортежей и **ValueTuple** типы, поля кортежа, чтения и записи; кортежи может изменяться.</span><span class="sxs-lookup"><span data-stu-id="dee23-198">In Visual Basic tuples and the **ValueTuple** types, tuple fields are read-write; the tuples are mutable.</span></span>

- <span data-ttu-id="dee23-199">Универсальный **кортежа** типы являются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="dee23-199">The generic **Tuple** types are reference types.</span></span> <span data-ttu-id="dee23-200">Используя эти **кортежа** типы означает выделение объектов.</span><span class="sxs-lookup"><span data-stu-id="dee23-200">Using these **Tuple** types means allocating objects.</span></span> <span data-ttu-id="dee23-201">В критических путях это может заметно влиять на производительность приложения.</span><span class="sxs-lookup"><span data-stu-id="dee23-201">On hot paths, this can have a measurable impact on your application's performance.</span></span> <span data-ttu-id="dee23-202">Visual Basic кортежей и **ValueTuple** типы являются типами значений.</span><span class="sxs-lookup"><span data-stu-id="dee23-202">Visual Basic tuples and the **ValueTuple** types are value types.</span></span>

<span data-ttu-id="dee23-203">Методы расширения в <xref:System.TupleExtensions> класс облегчить преобразование между кортежи Visual Basic и .NET **кортежа** объектов.</span><span class="sxs-lookup"><span data-stu-id="dee23-203">Extension methods in the <xref:System.TupleExtensions> class make it easy to convert between Visual Basic tuples and .NET **Tuple** objects.</span></span> <span data-ttu-id="dee23-204">**ToTuple** метод преобразует кортеж Visual Basic .NET **кортежа** объекта и **ToValueTuple** метод преобразует .NET **кортежа** Объект кортежа Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dee23-204">The **ToTuple** method converts a Visual Basic tuple to a .NET **Tuple** object, and the **ToValueTuple** method converts a .NET **Tuple** object to a Visual Basic tuple.</span></span>

<span data-ttu-id="dee23-205">Следующий пример создает кортеж, преобразует его в .NET **кортежа** объекта и преобразует его обратно кортеж Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dee23-205">The following example creates a tuple, converts it to a .NET **Tuple** object, and converts it back to a Visual Basic tuple.</span></span> <span data-ttu-id="dee23-206">Затем в примере сравнивается этот кортеж исходной версией, чтобы убедиться, что они равны.</span><span class="sxs-lookup"><span data-stu-id="dee23-206">The example then compares this tuple with the original one to ensure that they are equal.</span></span>

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a><span data-ttu-id="dee23-207">См. также</span><span class="sxs-lookup"><span data-stu-id="dee23-207">See also</span></span>

[<span data-ttu-id="dee23-208">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dee23-208">Visual Basic Language Reference</span></span>](index.md)  