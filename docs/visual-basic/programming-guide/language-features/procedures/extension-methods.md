---
title: Методы расширения (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: 1cc2ccef09dd027c6f1e82f60ed4ac5f50db6ebe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655288"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="f9e73-102">Методы расширения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9e73-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="f9e73-103">Методы расширения позволяют разработчикам добавлять пользовательские функциональные возможности для типов данных, которые уже определены без создания нового производного типа.</span><span class="sxs-lookup"><span data-stu-id="f9e73-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="f9e73-104">Методы расширения позволяют написать метод, который может вызываться, как если бы это был метод экземпляра существующего типа.</span><span class="sxs-lookup"><span data-stu-id="f9e73-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9e73-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="f9e73-105">Remarks</span></span>  
 <span data-ttu-id="f9e73-106">Метод расширения может быть только `Sub` процедуры или `Function` процедуры.</span><span class="sxs-lookup"><span data-stu-id="f9e73-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="f9e73-107">Нельзя определить свойство расширения, поле или событие.</span><span class="sxs-lookup"><span data-stu-id="f9e73-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="f9e73-108">Все методы расширения должны быть помечены атрибутом расширения `<Extension()>` из <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f9e73-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="f9e73-109">Первый параметр в определении метода расширения указывает тип данных, который расширяет метод.</span><span class="sxs-lookup"><span data-stu-id="f9e73-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="f9e73-110">При выполнении метода первый параметр привязан к экземпляру типа данных, который вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="f9e73-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9e73-111">Пример</span><span class="sxs-lookup"><span data-stu-id="f9e73-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f9e73-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f9e73-112">Description</span></span>  
 <span data-ttu-id="f9e73-113">В следующем примере определяется `Print` расширение <xref:System.String> тип данных.</span><span class="sxs-lookup"><span data-stu-id="f9e73-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="f9e73-114">Этот метод использует `Console.WriteLine` для отображения строки.</span><span class="sxs-lookup"><span data-stu-id="f9e73-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="f9e73-115">Параметр `Print` метода `aString`, устанавливает, что метод расширяет <xref:System.String> класса.</span><span class="sxs-lookup"><span data-stu-id="f9e73-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]  
  
 <span data-ttu-id="f9e73-116">Обратите внимание, что определение метода расширения помечено атрибутом расширения `<Extension()>`.</span><span class="sxs-lookup"><span data-stu-id="f9e73-116">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="f9e73-117">Помечать модуль, в которой определен метод является необязательным, но каждый метод расширения должен быть помечен.</span><span class="sxs-lookup"><span data-stu-id="f9e73-117">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="f9e73-118"><xref:System.Runtime.CompilerServices> Чтобы получить доступ к атрибуту расширения должен быть импортирован.</span><span class="sxs-lookup"><span data-stu-id="f9e73-118"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="f9e73-119">Методы расширения могут быть объявлены только внутри модулей.</span><span class="sxs-lookup"><span data-stu-id="f9e73-119">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="f9e73-120">Как правило модуль, в которой определен метод расширения не же модулем, в котором он вызван.</span><span class="sxs-lookup"><span data-stu-id="f9e73-120">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="f9e73-121">Вместо этого модуля, содержащего метод расширения импортируется, если необходимо, чтобы привести его в область.</span><span class="sxs-lookup"><span data-stu-id="f9e73-121">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="f9e73-122">После модуля, содержащего `Print` находится в области видимости, метод может быть вызван, как если бы он был обычным экземпляром метода, не принимающую аргументы, такие как `ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="f9e73-122">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]  
  
 <span data-ttu-id="f9e73-123">Следующий пример `PrintAndPunctuate`, также является расширением <xref:System.String>, определенным с помощью двух параметров.</span><span class="sxs-lookup"><span data-stu-id="f9e73-123">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="f9e73-124">Первый параметр `aString`, устанавливает, что метод расширения расширяет <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f9e73-124">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="f9e73-125">Второй параметр `punc`, должно быть строкой знаки пунктуации, передается в качестве аргумента при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="f9e73-125">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="f9e73-126">Метод отображает строку, следуют знаки пунктуации.</span><span class="sxs-lookup"><span data-stu-id="f9e73-126">The method displays the string followed by the punctuation marks.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]  
  
 <span data-ttu-id="f9e73-127">Метод вызывается отправкой аргумента строки для `punc`: `example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="f9e73-127">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="f9e73-128">В следующем примере показан `Print` и `PrintAndPunctuate` определен и вызывается.</span><span class="sxs-lookup"><span data-stu-id="f9e73-128">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="f9e73-129"><xref:System.Runtime.CompilerServices> импортируется в модуле определения для обеспечения доступа к атрибуту расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-129"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f9e73-130">Код</span><span class="sxs-lookup"><span data-stu-id="f9e73-130">Code</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="f9e73-131">Затем методы расширения добавлены в область действия и вызывается.</span><span class="sxs-lookup"><span data-stu-id="f9e73-131">Next, the extension methods are brought into scope and called.</span></span>  
  
```vb  
Imports ConsoleApplication2.StringExtensions  
Module Module1  
  
    Sub Main()  
  
        Dim example As String = "Example string"  
        example.Print()  
  
        example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="f9e73-132">Комментарии</span><span class="sxs-lookup"><span data-stu-id="f9e73-132">Comments</span></span>  
 <span data-ttu-id="f9e73-133">Все, что требуется для выполнения этих или подобных методов расширения является то, что они в области.</span><span class="sxs-lookup"><span data-stu-id="f9e73-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="f9e73-134">Если в области действия модуля, содержащего метод расширения, он отображается в IntelliSense и может вызываться, как если бы он был обычным экземпляром метода.</span><span class="sxs-lookup"><span data-stu-id="f9e73-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="f9e73-135">Обратите внимание, что при вызове методов, никакой аргумент не передается качестве первого параметра.</span><span class="sxs-lookup"><span data-stu-id="f9e73-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="f9e73-136">Параметр `aString` в предыдущий метод определения привязан к `example`, экземпляр `String` , вызывает их.</span><span class="sxs-lookup"><span data-stu-id="f9e73-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="f9e73-137">Компилятор будет использовать `example` в качестве аргумента, отправляемого в первый параметр.</span><span class="sxs-lookup"><span data-stu-id="f9e73-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="f9e73-138">Если метод расширения вызывается для объекта, который имеет значение `Nothing`, выполняет метод расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="f9e73-139">Это не относится к обычный методами экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f9e73-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="f9e73-140">Вы можете явно не проверять `Nothing` в методе расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-140">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="f9e73-141">Типы, которые могут быть расширены</span><span class="sxs-lookup"><span data-stu-id="f9e73-141">Types That Can Be Extended</span></span>  
 <span data-ttu-id="f9e73-142">Можно определить метод расширения большинства типов, которые могут быть представлены в списке параметров Visual Basic, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="f9e73-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
-   <span data-ttu-id="f9e73-143">Классы (ссылочные типы)</span><span class="sxs-lookup"><span data-stu-id="f9e73-143">Classes (reference types)</span></span>  
  
-   <span data-ttu-id="f9e73-144">Структуры (типы значений)</span><span class="sxs-lookup"><span data-stu-id="f9e73-144">Structures (value types)</span></span>  
  
-   <span data-ttu-id="f9e73-145">интерфейсов,</span><span class="sxs-lookup"><span data-stu-id="f9e73-145">Interfaces</span></span>  
  
-   <span data-ttu-id="f9e73-146">Делегаты</span><span class="sxs-lookup"><span data-stu-id="f9e73-146">Delegates</span></span>  
  
-   <span data-ttu-id="f9e73-147">Аргументы ByRef и ByVal</span><span class="sxs-lookup"><span data-stu-id="f9e73-147">ByRef and ByVal arguments</span></span>  
  
-   <span data-ttu-id="f9e73-148">Параметры универсального метода.</span><span class="sxs-lookup"><span data-stu-id="f9e73-148">Generic method parameters</span></span>  
  
-   <span data-ttu-id="f9e73-149">Массивы</span><span class="sxs-lookup"><span data-stu-id="f9e73-149">Arrays</span></span>  
  
 <span data-ttu-id="f9e73-150">Так как первый параметр указывает тип данных, который расширяет метод расширения, он является обязательным и не может быть необязательным.</span><span class="sxs-lookup"><span data-stu-id="f9e73-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="f9e73-151">По этой причине `Optional` параметры и `ParamArray` параметры не могут быть первый параметр в списке параметров.</span><span class="sxs-lookup"><span data-stu-id="f9e73-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="f9e73-152">Методы расширения не учитываются в позднего связывания.</span><span class="sxs-lookup"><span data-stu-id="f9e73-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="f9e73-153">В следующем примере инструкция `anObject.PrintMe()` вызывает <xref:System.MissingMemberException> исключения, которые появляются, если и то же исключение второй `PrintMe` определение метода расширения были удалены.</span><span class="sxs-lookup"><span data-stu-id="f9e73-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]  
  
## <a name="best-practices"></a><span data-ttu-id="f9e73-154">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="f9e73-154">Best Practices</span></span>  
 <span data-ttu-id="f9e73-155">Методы расширения предоставляют удобный и мощный способ расширить существующий тип.</span><span class="sxs-lookup"><span data-stu-id="f9e73-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="f9e73-156">Тем не менее для успешного использования, которые необходимо учитывать некоторые моменты.</span><span class="sxs-lookup"><span data-stu-id="f9e73-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="f9e73-157">Эти рекомендации применяются главным образом для авторов библиотек классов, но они могут повлиять на любое приложение, использующее методы расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="f9e73-158">Как правило методы расширения, добавленные к типам, которые вам не принадлежат более уязвимы чем методы расширения, добавленные к типам, которыми вы управляете.</span><span class="sxs-lookup"><span data-stu-id="f9e73-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="f9e73-159">Количество операций, может возникнуть в классах, которые вам не принадлежат, могут конфликтовать с методами расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
-   <span data-ttu-id="f9e73-160">Если существует любой доступный элемент экземпляра, который имеет сигнатуру, совместимую с аргументами в вызывающей инструкции, при этом сужающие преобразования не требуется для параметра от аргумента, метод экземпляра будет использоваться в предпочтение любому методу расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="f9e73-161">Таким образом Если соответствующий метод экземпляра добавляется в класс в некоторой точке, существующий элемент расширения, основанные на могут стать недоступными.</span><span class="sxs-lookup"><span data-stu-id="f9e73-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
-   <span data-ttu-id="f9e73-162">Автор метода расширения не может помешать другим программистам записать конфликтующие методы расширения, которые могут иметь приоритет над исходным расширением.</span><span class="sxs-lookup"><span data-stu-id="f9e73-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
-   <span data-ttu-id="f9e73-163">Надежность можно повысить, помещая методы расширения в свое собственное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="f9e73-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="f9e73-164">Потребители библиотеки можно включить пространство имен или исключить его или выбрать пространства имен отдельно от остальной части библиотеки.</span><span class="sxs-lookup"><span data-stu-id="f9e73-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
-   <span data-ttu-id="f9e73-165">Он может оказаться более безопасным расширить интерфейсы, чем расширения классов, особенно в том случае, если вы не являетесь владельцем интерфейса или класса.</span><span class="sxs-lookup"><span data-stu-id="f9e73-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="f9e73-166">Изменения в интерфейсе влияет на каждый класс, который его реализует.</span><span class="sxs-lookup"><span data-stu-id="f9e73-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="f9e73-167">Таким образом автор, можно снизить вероятность для добавления или изменения методов в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="f9e73-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="f9e73-168">Однако если класс реализует два интерфейса, имеющих методы расширения с такой же сигнатурой, ни один из методов расширения не виден.</span><span class="sxs-lookup"><span data-stu-id="f9e73-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
-   <span data-ttu-id="f9e73-169">Расширить наиболее конкретный тип, который вы можете.</span><span class="sxs-lookup"><span data-stu-id="f9e73-169">Extend the most specific type you can.</span></span> <span data-ttu-id="f9e73-170">В иерархии типов Если выбран тип, от которого наследуются другие типы, существуют уровни возможностей для введения методов экземпляра или других методов расширения, которые могут конфликтовать с вашими.</span><span class="sxs-lookup"><span data-stu-id="f9e73-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="f9e73-171">Методы расширения, методы экземпляра и свойства</span><span class="sxs-lookup"><span data-stu-id="f9e73-171">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="f9e73-172">Когда метод экземпляра в области имеет сигнатуру, совместимую с аргументом вызывающего оператора, метод экземпляра выбирается в предпочтение любому методу расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="f9e73-173">Метод экземпляра имеет более высокий приоритет, даже если метод расширения является более подходящим.</span><span class="sxs-lookup"><span data-stu-id="f9e73-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="f9e73-174">В следующем примере `ExampleClass` содержит метод экземпляра с именем `ExampleMethod` , имеющий один параметр типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="f9e73-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="f9e73-175">Метод расширения `ExampleMethod` расширяет `ExampleClass`, и имеет один параметр типа `Long`.</span><span class="sxs-lookup"><span data-stu-id="f9e73-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]  
  
 <span data-ttu-id="f9e73-176">Первый вызов `ExampleMethod` в следующий код вызывает метод расширения, поскольку `arg1` — `Long` и совместим только с `Long` параметр метода расширения.</span><span class="sxs-lookup"><span data-stu-id="f9e73-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="f9e73-177">Второй вызов `ExampleMethod` имеет `Integer` аргумент, `arg2`, и он вызывает метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f9e73-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]  
  
 <span data-ttu-id="f9e73-178">Теперь обратный типы данных параметров двумя способами:</span><span class="sxs-lookup"><span data-stu-id="f9e73-178">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]  
  
 <span data-ttu-id="f9e73-179">Код в `Main` вызывает метод экземпляра оба раза.</span><span class="sxs-lookup"><span data-stu-id="f9e73-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="f9e73-180">Это, поскольку оба `arg1` и `arg2` иметь расширяющее преобразование `Long`, а метод экземпляра имеет преимущество перед методом расширения в обоих случаях.</span><span class="sxs-lookup"><span data-stu-id="f9e73-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]  
  
 <span data-ttu-id="f9e73-181">Таким образом метод расширения не может заменить существующий метод экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f9e73-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="f9e73-182">Тем не менее если метод расширения имеет то же имя, что и метод экземпляра, но подписи не конфликтуют, оба метода может быть доступен.</span><span class="sxs-lookup"><span data-stu-id="f9e73-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="f9e73-183">Например если класс `ExampleClass` содержит метод с именем `ExampleMethod` , не имеющий аргументов, методы расширения с тем же именем, но различными сигнатурами, допускаются, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="f9e73-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]  
  
 <span data-ttu-id="f9e73-184">Результат выполнения этого кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f9e73-184">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="f9e73-185">Ситуация выглядит проще со свойствами: Если метод расширения имеет имя, совпадающее с именем свойства класса, который он расширяет, метод расширения не отображается и не доступен.</span><span class="sxs-lookup"><span data-stu-id="f9e73-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="f9e73-186">Приоритет метода расширения</span><span class="sxs-lookup"><span data-stu-id="f9e73-186">Extension Method Precedence</span></span>  
 <span data-ttu-id="f9e73-187">Когда два метода расширения, имеющие одинаковые сигнатуры в области и доступны, будет вызван метод с более высоким приоритетом.</span><span class="sxs-lookup"><span data-stu-id="f9e73-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="f9e73-188">Приоритет метода расширения основан на механизм, используемый для переноса метода в область.</span><span class="sxs-lookup"><span data-stu-id="f9e73-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="f9e73-189">Ниже перечислены иерархии приоритета, от наибольшего к наименьшему.</span><span class="sxs-lookup"><span data-stu-id="f9e73-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1.  <span data-ttu-id="f9e73-190">Методы расширения, определенные внутри текущего модуля.</span><span class="sxs-lookup"><span data-stu-id="f9e73-190">Extension methods defined inside the current module.</span></span>  
  
2.  <span data-ttu-id="f9e73-191">Методы расширения определенные внутри типов данных в текущем пространстве имен или один из его родительских объектов с дочерними пространствами имен, имеющими более высокий приоритет, чем родительские пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f9e73-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3.  <span data-ttu-id="f9e73-192">Методы расширения, определенные внутри любых импортов типа в текущем файле.</span><span class="sxs-lookup"><span data-stu-id="f9e73-192">Extension methods defined inside any type imports in the current file.</span></span>  
  
4.  <span data-ttu-id="f9e73-193">Методы расширения, определенные внутри любых импортов пространства имен в текущем файле.</span><span class="sxs-lookup"><span data-stu-id="f9e73-193">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5.  <span data-ttu-id="f9e73-194">Методы расширения, определенные внутри любых импортов типов на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="f9e73-194">Extension methods defined inside any project-level type imports.</span></span>  
  
6.  <span data-ttu-id="f9e73-195">Методы расширения, определенные внутри любых импортов пространства имен на уровне проекта.</span><span class="sxs-lookup"><span data-stu-id="f9e73-195">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="f9e73-196">Если приоритет не позволяет устранить неоднозначность, можно использовать полное доменное имя для указания метода, который вы вызываете.</span><span class="sxs-lookup"><span data-stu-id="f9e73-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="f9e73-197">Если `Print` метод в предыдущем примере определен в модуле с именем `StringExtensions`, полное доменное имя является `StringExtensions.Print(example)` вместо `example.Print()`.</span><span class="sxs-lookup"><span data-stu-id="f9e73-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9e73-198">См. также</span><span class="sxs-lookup"><span data-stu-id="f9e73-198">See Also</span></span>  
 <xref:System.Runtime.CompilerServices>  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [<span data-ttu-id="f9e73-199">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="f9e73-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [<span data-ttu-id="f9e73-200">Оператор Module</span><span class="sxs-lookup"><span data-stu-id="f9e73-200">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="f9e73-201">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="f9e73-201">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f9e73-202">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="f9e73-202">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="f9e73-203">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="f9e73-203">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="f9e73-204">Обзор атрибутов</span><span class="sxs-lookup"><span data-stu-id="f9e73-204">Attributes overview</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="f9e73-205">Область в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9e73-205">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
