---
title: Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: a1c1b7c247d3277c6614a4774395650c4c069c2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644307"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="62fc8-102">Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62fc8-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="62fc8-103">Можно наследовать классы Visual Basic из `Public` классов в COM-объектами, даже тех, которые созданы в более ранних версиях Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="62fc8-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="62fc8-104">Свойства и методы классов, унаследованных от объектов COM можно переопределить или перегрузить только как свойства и методы базового класса можно переопределить или перегружен.</span><span class="sxs-lookup"><span data-stu-id="62fc8-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="62fc8-105">Наследование от объектов COM полезно при наличии существующей библиотеки класса, не требуется повторной компиляции.</span><span class="sxs-lookup"><span data-stu-id="62fc8-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="62fc8-106">Ниже показано, как использовать Visual Basic 6.0 для создания COM-объекта, содержащего класс и его использование в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="62fc8-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="62fc8-107">Для создания COM-объекта, который используется в этом пошаговом руководстве</span><span class="sxs-lookup"><span data-stu-id="62fc8-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="62fc8-108">В Visual Basic 6.0 откройте новый проект ActiveX библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="62fc8-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="62fc8-109">Проект с именем `Project1` создается.</span><span class="sxs-lookup"><span data-stu-id="62fc8-109">A project named `Project1` is created.</span></span> <span data-ttu-id="62fc8-110">Он имеет класс с именем `Class1`.</span><span class="sxs-lookup"><span data-stu-id="62fc8-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="62fc8-111">В **обозревателя проектов**, щелкните правой кнопкой мыши **Project1**, а затем нажмите кнопку **свойства Project1**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="62fc8-112">**Свойства проекта** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="62fc8-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="62fc8-113">На **Общие** вкладке **свойства проекта** диалоговом окне измените имя проекта, введя `ComObject1` в **имя проекта** поля.</span><span class="sxs-lookup"><span data-stu-id="62fc8-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="62fc8-114">В **обозревателя проектов**, щелкните правой кнопкой мыши `Class1`, а затем нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="62fc8-115">**Свойства** откроется окно для класса.</span><span class="sxs-lookup"><span data-stu-id="62fc8-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="62fc8-116">Изменение `Name` свойства `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="62fc8-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="62fc8-117">В **обозревателя проектов**, щелкните правой кнопкой мыши `MathFunctions`, а затем нажмите кнопку **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="62fc8-118">**Редактор кода** отображается.</span><span class="sxs-lookup"><span data-stu-id="62fc8-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="62fc8-119">Добавьте локальную переменную для хранения значения свойства:</span><span class="sxs-lookup"><span data-stu-id="62fc8-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="62fc8-120">Добавить свойство `Let` и свойство `Get` процедуры свойств:</span><span class="sxs-lookup"><span data-stu-id="62fc8-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
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
  
9. <span data-ttu-id="62fc8-121">Добавление функции:</span><span class="sxs-lookup"><span data-stu-id="62fc8-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="62fc8-122">Создайте и зарегистрируйте объект COM, щелкнув **Создать ComObject1.dll** на **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="62fc8-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62fc8-123">Несмотря на то, что также можно представить класс, созданный с помощью Visual Basic как объект COM, он не является объектом COM и не может использоваться в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="62fc8-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="62fc8-124">Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="62fc8-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="62fc8-125">Сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="62fc8-125">Interop Assemblies</span></span>  
 <span data-ttu-id="62fc8-126">В следующей процедуре вы создадите сборку взаимодействия, которая выступает в качестве моста между неуправляемого кода (например, объект COM) и управляемым кодом, который использует Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="62fc8-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="62fc8-127">Сборки взаимодействия, который создает Visual Basic обрабатывает большую часть особенностей работы с объектами COM, такие как *маршалинг взаимодействия*, процесс упаковки параметров и возвращаемых значений, в эквивалентное ему данные типы, как они перемещаются и из COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="62fc8-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="62fc8-128">Сборку взаимодействия, а не к самому объекту COM. указывает ссылка в приложение Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="62fc8-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="62fc8-129">Для использования COM-объекта с Visual Basic 2005 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="62fc8-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="62fc8-130">Откройте новый проект приложения Windows на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="62fc8-130">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="62fc8-131">В меню **Проект** щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="62fc8-132">Появится диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="62fc8-133">На **COM** дважды щелкните `ComObject1` в **имя компонента** списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="62fc8-134">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="62fc8-135">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="62fc8-136">В **шаблоны** области, нажмите кнопку **класса**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="62fc8-137">Имя файла по умолчанию `Class1.vb`, отображается в **имя** поля.</span><span class="sxs-lookup"><span data-stu-id="62fc8-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="62fc8-138">Измените значение поля на MathClass.vb и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="62fc8-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="62fc8-139">При этом создается класс с именем `MathClass`и отображает его код.</span><span class="sxs-lookup"><span data-stu-id="62fc8-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="62fc8-140">Добавьте следующий код в начало `MathClass` для наследования от класса COM.</span><span class="sxs-lookup"><span data-stu-id="62fc8-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  <span data-ttu-id="62fc8-141">Перегрузите открытый метод базового класса, добавив следующий код в `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="62fc8-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  <span data-ttu-id="62fc8-142">Расширьте наследуемый класс, добавив следующий код в `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="62fc8-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 <span data-ttu-id="62fc8-143">Новый класс наследует свойства базового класса в COM-объекта, перегружает метод и определяет новый метод для расширения класса.</span><span class="sxs-lookup"><span data-stu-id="62fc8-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="62fc8-144">Чтобы проверить унаследованный класс</span><span class="sxs-lookup"><span data-stu-id="62fc8-144">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="62fc8-145">Добавьте в форму запуска и дважды щелкните его, чтобы просмотреть код.</span><span class="sxs-lookup"><span data-stu-id="62fc8-145">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="62fc8-146">На кнопке панели `Click` процедуры обработчика событий, добавьте следующий код для создания экземпляра `MathClass` и вызовите перегруженные методы:</span><span class="sxs-lookup"><span data-stu-id="62fc8-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  <span data-ttu-id="62fc8-147">Запустите проект, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="62fc8-147">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="62fc8-148">При нажатии кнопки в форме `AddNumbers` сначала вызывается метод с `Short` чисел, тип данных и Visual Basic выбирает соответствующий метод из базового класса.</span><span class="sxs-lookup"><span data-stu-id="62fc8-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="62fc8-149">Второй вызов `AddNumbers` направляется в перегруженный метод `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="62fc8-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="62fc8-150">Третий вызов вызовы `SubtractNumbers` метод, который расширяет класс.</span><span class="sxs-lookup"><span data-stu-id="62fc8-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="62fc8-151">Свойство в базовом классе, и выводится значение.</span><span class="sxs-lookup"><span data-stu-id="62fc8-151">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="62fc8-152">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="62fc8-152">Next Steps</span></span>  
 <span data-ttu-id="62fc8-153">Возможно, вы заметили, перегруженных `AddNumbers` имеет тот же тип данных, метод, унаследованный от базового класса COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="62fc8-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="62fc8-154">Это так, как аргументы и параметры метода базового класса определены как 16-битовых целых чисел в Visual Basic 6.0, но они представляются как 16-битовых целых чисел типа `Short` в более поздних версиях Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="62fc8-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="62fc8-155">Новая функция поддерживает 32-битовых целых чисел и перегружает функцию базового класса.</span><span class="sxs-lookup"><span data-stu-id="62fc8-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="62fc8-156">При работе с COM-объектами, убедиться в том, что размер и типы данных параметров.</span><span class="sxs-lookup"><span data-stu-id="62fc8-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="62fc8-157">Например при использовании COM-объекта, который принимает в качестве аргумента объект коллекции Visual Basic 6.0 не предоставляют набор из более поздней версии Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="62fc8-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="62fc8-158">Свойства и методы, унаследованные из классов COM можно переопределить, это означает, что можно объявить локальное свойство или метод, который заменяет свойство или метод, унаследованный от базового класса COM.</span><span class="sxs-lookup"><span data-stu-id="62fc8-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="62fc8-159">Правила переопределения наследуемых свойств COM аналогичны правилам переопределения других свойств и методов со следующими исключениями:</span><span class="sxs-lookup"><span data-stu-id="62fc8-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="62fc8-160">При переопределении свойства или методы, унаследованные от класса COM, необходимо переопределить все остальные унаследованные свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="62fc8-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="62fc8-161">Свойства, использующие `ByRef` параметров не может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="62fc8-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62fc8-162">См. также</span><span class="sxs-lookup"><span data-stu-id="62fc8-162">See Also</span></span>  
 [<span data-ttu-id="62fc8-163">COM-взаимодействие в приложениях .NET Framework</span><span class="sxs-lookup"><span data-stu-id="62fc8-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="62fc8-164">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="62fc8-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="62fc8-165">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="62fc8-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
