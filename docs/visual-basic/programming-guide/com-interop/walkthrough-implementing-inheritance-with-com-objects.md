---
title: "Пошаговое руководство: Реализация наследования с использованием COM-объектов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- inheritance, COM reusability
- base classes, COM reusability
- inheritance, walkthroughs
- derived classes, COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0e816d1728678467d930de524b894d175f9b0c0a
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="ee3c4-102">Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee3c4-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="ee3c4-103">Создавать производные классы Visual Basic из можно `Public` классов в COM-объекты, даже те, которые созданы в более ранних версиях [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee3c4-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="ee3c4-104">Свойства и методы классов, унаследованных от объектов COM можно переопределить или перегрузить как свойства и методы базового класса можно переопределить или перегружен.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="ee3c4-105">Наследование от объектов COM используется, при наличии созданную библиотеку классов нежелательно перекомпилировать.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="ee3c4-106">Ниже показано, как использовать Visual Basic 6.0 для создания COM-объект, содержащий класс, а затем использовать его в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="ee3c4-107">Чтобы создать объект COM, используемый в данном пошаговом руководстве</span><span class="sxs-lookup"><span data-stu-id="ee3c4-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="ee3c4-108">В Visual Basic 6.0 откройте новый проект ActiveX DLL.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="ee3c4-109">Проект с именем `Project1` создается.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-109">A project named `Project1` is created.</span></span> <span data-ttu-id="ee3c4-110">Он имеет класс с именем `Class1`.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="ee3c4-111">В **обозревателя проектов**, щелкните правой кнопкой мыши **Project1**, а затем нажмите кнопку **свойства Project1**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="ee3c4-112">**Свойства проекта** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="ee3c4-113">На **Общие** вкладке **свойства проекта** диалоговом окне измените имя проекта, введя `ComObject1` в **имя проекта** поле.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="ee3c4-114">В **обозревателя проектов**, щелкните правой кнопкой мыши `Class1`, а затем нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="ee3c4-115">**Свойства** откроется окно для класса.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="ee3c4-116">Изменение `Name` свойства `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="ee3c4-117">В **обозревателя проектов**, щелкните правой кнопкой мыши `MathFunctions`, а затем нажмите кнопку **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="ee3c4-118">**Редактор кода** отображается.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="ee3c4-119">Добавьте локальную переменную для хранения значения свойства:</span><span class="sxs-lookup"><span data-stu-id="ee3c4-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="ee3c4-120">Добавьте свойство `Let` и свойство `Get` процедуры свойств:</span><span class="sxs-lookup"><span data-stu-id="ee3c4-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. <span data-ttu-id="ee3c4-121">Добавьте функцию:</span><span class="sxs-lookup"><span data-stu-id="ee3c4-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="ee3c4-122">Создайте и зарегистрируйте объект COM, щелкнув **Создать ComObject1.dll** на **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ee3c4-123">Несмотря на то, что пользователь может предоставить класс, созданный в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] как COM-объект не является объектом COM и не может использоваться в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-123">Although you can also expose a class created with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="ee3c4-124">Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="ee3c4-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="ee3c4-125">Сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="ee3c4-125">Interop Assemblies</span></span>  
 <span data-ttu-id="ee3c4-126">В следующей процедуре будет создать сборку взаимодействия, которая действует как мост между неуправляемым кодом (например, объект COM) и управляемым кодом [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] использует.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] uses.</span></span> <span data-ttu-id="ee3c4-127">Сборки взаимодействия, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] обеспечивает различные аспекты работы с COM-объектами, такие как *маршалинг взаимодействия*, процесс упаковки параметров и возвращения значений в данных типов при передаче в объекты COM и обратно.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-127">The interop assembly that [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="ee3c4-128">Ссылка в [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] точки приложения сборку взаимодействия, а не к самому объекту COM..</span><span class="sxs-lookup"><span data-stu-id="ee3c4-128">The reference in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="ee3c4-129">Для использования COM-объекта с помощью Visual Basic 2005 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="ee3c4-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="ee3c4-130">Откройте новую [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] проекта приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-130">Open a new [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="ee3c4-131">На **проекта** меню, щелкните **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="ee3c4-132">**Добавить ссылку** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="ee3c4-133">На **COM** дважды щелкните `ComObject1` в **имя компонента** списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="ee3c4-134">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="ee3c4-135">**Add New Item** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="ee3c4-136">В **шаблоны** область, нажмите кнопку **класса**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="ee3c4-137">Имя файла по умолчанию `Class1.vb`, отображается в **имя** поле.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="ee3c4-138">Измените значение поля на MathClass.vb и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="ee3c4-139">При этом создается класс с именем `MathClass`и отобразит его код.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="ee3c4-140">Добавьте следующий код в начало `MathClass` для наследования от класса COM.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     <span data-ttu-id="ee3c4-141">[!code-vb[VbVbalrInterop&#31;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ee3c4-141">[!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span></span>  
  
7.  <span data-ttu-id="ee3c4-142">Перегрузите открытый метод базового класса, добавив следующий код в `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="ee3c4-142">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="ee3c4-143">[!code-vb[VbVbalrInterop&#32;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ee3c4-143">[!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span></span>  
  
8.  <span data-ttu-id="ee3c4-144">Расширьте наследуемый класс, добавив следующий код в `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="ee3c4-144">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="ee3c4-145">[!code-vb[VbVbalrInterop&#33;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ee3c4-145">[!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span></span>  
  
 <span data-ttu-id="ee3c4-146">Новый класс наследует свойства базового класса в объекте COM, перегружает метод и определяет новый метод для расширения класса.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-146">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="ee3c4-147">Чтобы проверить унаследованный класс</span><span class="sxs-lookup"><span data-stu-id="ee3c4-147">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="ee3c4-148">Добавьте кнопку в форму запуска и дважды щелкните его для просмотра его кода.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-148">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="ee3c4-149">Для кнопки `Click` процедуры обработчика событий, добавьте следующий код для создания экземпляра `MathClass` и вызовите перегруженные методы:</span><span class="sxs-lookup"><span data-stu-id="ee3c4-149">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     <span data-ttu-id="ee3c4-150">[!code-vb[VbVbalrInterop&#34;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ee3c4-150">[!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span></span>  
  
3.  <span data-ttu-id="ee3c4-151">Запустите проект, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-151">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="ee3c4-152">При нажатии кнопки в форме `AddNumbers` сначала вызывается метод с `Short` чисел, тип данных и [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] выбирает соответствующий метод из базового класса.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-152">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chooses the appropriate method from the base class.</span></span> <span data-ttu-id="ee3c4-153">Второй вызов `AddNumbers` направляется в перегруженный метод `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-153">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="ee3c4-154">Третий вызов вызовы `SubtractNumbers` метод, который расширяет класс.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-154">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="ee3c4-155">Свойство в базовом классе, и отображается значение.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-155">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ee3c4-156">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="ee3c4-156">Next Steps</span></span>  
 <span data-ttu-id="ee3c4-157">Вы могли заметить, перегруженных `AddNumbers` имеет тот же тип данных, метод, унаследованный от базового класса COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-157">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="ee3c4-158">Это потому, что аргументы и параметры метода базового класса определены как 16-битовых целых чисел в Visual Basic 6.0, но они представляются как 16-битовых целых чисел типа `Short` в более поздних версиях Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-158">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="ee3c4-159">Новая функция поддерживает 32-разрядные целые значения и перегружает функцию базового класса.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-159">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="ee3c4-160">При работе с COM-объектами, убедитесь в правильности размера и типов данных параметров.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-160">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="ee3c4-161">Например при использовании COM-объекта, который принимает в качестве аргумента объект коллекции Visual Basic 6.0, невозможно использовать коллекцию из более поздней версии Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-161">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="ee3c4-162">Свойства и методы, унаследованные из классов COM можно переопределить, это означает, что можно объявить локальное свойство или метод, который заменяет свойство или метод, унаследованный от базового класса COM.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-162">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="ee3c4-163">Правила переопределения унаследованных свойств COM аналогичны правилам переопределения других свойств и методов со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="ee3c4-163">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="ee3c4-164">При переопределении свойства или методы, унаследованные от класса COM, необходимо переопределить все остальные унаследованные свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-164">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="ee3c4-165">Свойства, использующие `ByRef` параметров не может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="ee3c4-165">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee3c4-166">См. также</span><span class="sxs-lookup"><span data-stu-id="ee3c4-166">See Also</span></span>  
 <span data-ttu-id="ee3c4-167">[COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="ee3c4-167">[COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="ee3c4-168"> [Оператор Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ee3c4-168"> [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="ee3c4-169"> [Тип данных Short](../../../visual-basic/language-reference/data-types/short-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="ee3c4-169"> [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)</span></span>
