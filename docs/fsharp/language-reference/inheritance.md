---
title: "Наследование (F#)"
description: "Дополнительные сведения о определить отношения наследования F #, с помощью ключевого слова «inherit»."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b38ab2f6-7ba7-4839-8eff-e6bd6cfd2b2f
ms.openlocfilehash: 331c8f4e39aacd9d5e55bfbaf584f037e58d36a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="inheritance"></a><span data-ttu-id="5e860-104">Наследование</span><span class="sxs-lookup"><span data-stu-id="5e860-104">Inheritance</span></span>

<span data-ttu-id="5e860-105">Наследование, используемое для моделирования связи «is-a» или подтипов в объектно ориентированного программирования.</span><span class="sxs-lookup"><span data-stu-id="5e860-105">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>


## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="5e860-106">Определение отношений наследования</span><span class="sxs-lookup"><span data-stu-id="5e860-106">Specifying Inheritance Relationships</span></span>
<span data-ttu-id="5e860-107">Определить отношения наследования с помощью `inherit` ключевое слово в объявлении класса.</span><span class="sxs-lookup"><span data-stu-id="5e860-107">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="5e860-108">В следующем примере показан Базовая синтаксическая форма.</span><span class="sxs-lookup"><span data-stu-id="5e860-108">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="5e860-109">Класс может иметь не более одного прямого базового класса.</span><span class="sxs-lookup"><span data-stu-id="5e860-109">A class can have at most one direct base class.</span></span> <span data-ttu-id="5e860-110">Если не указать базовый класс с помощью `inherit` ключевое слово, то класс неявно наследуется от `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="5e860-110">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>


## <a name="inherited-members"></a><span data-ttu-id="5e860-111">Наследуемые члены</span><span class="sxs-lookup"><span data-stu-id="5e860-111">Inherited Members</span></span>
<span data-ttu-id="5e860-112">Если класс наследуется от другого класса, методы и члены базового класса доступны пользователям производного класса, как будто они являются непосредственными членами производного класса.</span><span class="sxs-lookup"><span data-stu-id="5e860-112">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="5e860-113">Все привязки let и параметры конструктора являются закрытыми для класса и, таким образом, нельзя обращаться из производных классов.</span><span class="sxs-lookup"><span data-stu-id="5e860-113">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="5e860-114">Ключевое слово `base` доступно в производных классах и относится к экземпляру базового класса.</span><span class="sxs-lookup"><span data-stu-id="5e860-114">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="5e860-115">Он используется как идентификатор самого себя.</span><span class="sxs-lookup"><span data-stu-id="5e860-115">It is used like the self-identifier.</span></span>


## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="5e860-116">Виртуальные методы и переопределение</span><span class="sxs-lookup"><span data-stu-id="5e860-116">Virtual Methods and Overrides</span></span>
<span data-ttu-id="5e860-117">Виртуальные методы (и свойства) работают иначе в F # по сравнению с другими языками .NET.</span><span class="sxs-lookup"><span data-stu-id="5e860-117">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="5e860-118">Чтобы объявить новый виртуальный член, следует использовать `abstract` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="5e860-118">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="5e860-119">Это делается независимо от того, может ли предоставлять реализацию по умолчанию для этого метода.</span><span class="sxs-lookup"><span data-stu-id="5e860-119">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="5e860-120">Таким образом, полное определение виртуального метода в базовом классе имеет следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="5e860-120">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="5e860-121">И в производном классе, переопределение данного виртуального метода имеет следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="5e860-121">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="5e860-122">Если опустить реализацию по умолчанию в базовом классе, базовый класс становится абстрактным классом.</span><span class="sxs-lookup"><span data-stu-id="5e860-122">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="5e860-123">В следующем примере кода показано объявление нового виртуального метода `function1` в базовом классе и его можно переопределить в производном классе.</span><span class="sxs-lookup"><span data-stu-id="5e860-123">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]
    
## <a name="constructors-and-inheritance"></a><span data-ttu-id="5e860-124">Конструкторы и наследование</span><span class="sxs-lookup"><span data-stu-id="5e860-124">Constructors and Inheritance</span></span>
<span data-ttu-id="5e860-125">Необходимо вызвать конструктор базового класса в производном классе.</span><span class="sxs-lookup"><span data-stu-id="5e860-125">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="5e860-126">Аргументы для конструктора базового класса отображаются в списке аргументов в `inherit` предложения.</span><span class="sxs-lookup"><span data-stu-id="5e860-126">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="5e860-127">Используемые значения необходимо определять из аргументов, передаваемых в конструктор производного класса.</span><span class="sxs-lookup"><span data-stu-id="5e860-127">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="5e860-128">В следующем коде показано базовый класс и производный класс, в которых производного класса вызывает конструктор базового класса в выражении inherit:</span><span class="sxs-lookup"><span data-stu-id="5e860-128">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="5e860-129">В случае несколько конструкторов можно использовать следующий код.</span><span class="sxs-lookup"><span data-stu-id="5e860-129">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="5e860-130">Первая строка конструкторов в производных классах `inherit` предложение, а также поля отображаются как явные поля, объявленные с `val` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="5e860-130">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="5e860-131">Дополнительные сведения см. в разделе [явные поля: `val` ключевое слово](members/explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="5e860-131">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="5e860-132">Альтернативы для наследования</span><span class="sxs-lookup"><span data-stu-id="5e860-132">Alternatives to Inheritance</span></span>
<span data-ttu-id="5e860-133">В случаях, где требуется незначительное изменение типа следует использовать выражение объекта вместо наследования.</span><span class="sxs-lookup"><span data-stu-id="5e860-133">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="5e860-134">Следующий пример иллюстрирует использование выражения объекта в качестве альтернативы для создания нового производного типа:</span><span class="sxs-lookup"><span data-stu-id="5e860-134">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="5e860-135">Дополнительные сведения о выражениях объектов см. в разделе [выражения объекта](object-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="5e860-135">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="5e860-136">При создании иерархии объектов, рассмотрите возможность использования размеченного объединения вместо наследования.</span><span class="sxs-lookup"><span data-stu-id="5e860-136">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="5e860-137">Размеченные объединения, можно моделировать изменение поведения различных объектов, имеющих общий тип.</span><span class="sxs-lookup"><span data-stu-id="5e860-137">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="5e860-138">Использование одного размеченного объединения часто позволяет избавиться от необходимости для нескольких производных классов, которые незначительно отличаются друг от друга.</span><span class="sxs-lookup"><span data-stu-id="5e860-138">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="5e860-139">Сведения о размеченные объединения см. в разделе [размеченные объединения](discriminated-unions.md).</span><span class="sxs-lookup"><span data-stu-id="5e860-139">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="5e860-140">См. также</span><span class="sxs-lookup"><span data-stu-id="5e860-140">See Also</span></span>
[<span data-ttu-id="5e860-141">Выражения объекта</span><span class="sxs-lookup"><span data-stu-id="5e860-141">Object Expressions</span></span>](object-expressions.md)

[<span data-ttu-id="5e860-142">Справочник по языку F#</span><span class="sxs-lookup"><span data-stu-id="5e860-142">F# Language Reference</span></span>](index.md)