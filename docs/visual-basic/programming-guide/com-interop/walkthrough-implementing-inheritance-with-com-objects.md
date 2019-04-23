---
title: Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 0b3977e73e3b2aa9e80e2dab08d15035283b8387
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334150"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="77c32-102">Пошаговое руководство. Реализация наследования с использованием COM-объектов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77c32-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="77c32-103">Можно создавать классы Visual Basic из `Public` классов в COM-объекты, даже были созданы в более ранних версиях Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77c32-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="77c32-104">Свойства и методы классов, унаследованных от объектов COM могут быть переопределены или перегружены так же, как свойства и методы базового класса могут быть переопределены или перегружены.</span><span class="sxs-lookup"><span data-stu-id="77c32-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="77c32-105">Наследование от COM-объектов используется, при наличии существующей библиотеки класса, перекомпиляция не требуется.</span><span class="sxs-lookup"><span data-stu-id="77c32-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="77c32-106">Ниже показано, как использовать Visual Basic 6.0 для создания COM-объект, который содержит класс, а затем использовать его в качестве базового класса.</span><span class="sxs-lookup"><span data-stu-id="77c32-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="77c32-107">Для создания COM-объект, который используется в этом пошаговом руководстве</span><span class="sxs-lookup"><span data-stu-id="77c32-107">To build the COM object that is used in this walkthrough</span></span>  
  
1. <span data-ttu-id="77c32-108">В Visual Basic 6.0 откройте новый проект ActiveX библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="77c32-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="77c32-109">Проект с именем `Project1` создается.</span><span class="sxs-lookup"><span data-stu-id="77c32-109">A project named `Project1` is created.</span></span> <span data-ttu-id="77c32-110">Он имеет класс с именем `Class1`.</span><span class="sxs-lookup"><span data-stu-id="77c32-110">It has a class named `Class1`.</span></span>  
  
2. <span data-ttu-id="77c32-111">В **обозревателя проектов**, щелкните правой кнопкой мыши **Project1**, а затем нажмите кнопку **свойства Project1**.</span><span class="sxs-lookup"><span data-stu-id="77c32-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="77c32-112">**Свойства проекта** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="77c32-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3. <span data-ttu-id="77c32-113">На **Общие** вкладке **свойства проекта** диалогового окна можно изменить имя проекта, введя `ComObject1` в **имя_проекта** поля.</span><span class="sxs-lookup"><span data-stu-id="77c32-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4. <span data-ttu-id="77c32-114">В **обозревателя проектов**, щелкните правой кнопкой мыши `Class1`, а затем нажмите кнопку **свойства**.</span><span class="sxs-lookup"><span data-stu-id="77c32-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="77c32-115">**Свойства** откроется диалоговое окно для класса.</span><span class="sxs-lookup"><span data-stu-id="77c32-115">The **Properties** window for the class is displayed.</span></span>  
  
5. <span data-ttu-id="77c32-116">Изменение `Name` свойства `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="77c32-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6. <span data-ttu-id="77c32-117">В **обозревателя проектов**, щелкните правой кнопкой мыши `MathFunctions`, а затем нажмите кнопку **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="77c32-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="77c32-118">**Редактор кода** отображается.</span><span class="sxs-lookup"><span data-stu-id="77c32-118">The **Code Editor** is displayed.</span></span>  
  
7. <span data-ttu-id="77c32-119">Добавьте локальную переменную для хранения значения свойства:</span><span class="sxs-lookup"><span data-stu-id="77c32-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8. <span data-ttu-id="77c32-120">Добавить свойство `Let` и свойство `Get` процедуры свойств:</span><span class="sxs-lookup"><span data-stu-id="77c32-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
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
  
9. <span data-ttu-id="77c32-121">Добавление функции:</span><span class="sxs-lookup"><span data-stu-id="77c32-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="77c32-122">Создание и регистрация COM-объект, щелкнув **Создать ComObject1.dll** на **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="77c32-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77c32-123">Несмотря на то, что пользователь может предоставить класс, созданный в Visual Basic как объект COM, он не является истинным COM-объектом и не может использоваться в этом пошаговом руководстве.</span><span class="sxs-lookup"><span data-stu-id="77c32-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="77c32-124">Дополнительные сведения см. в разделе [COM-взаимодействие в приложениях .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="77c32-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="77c32-125">Сборки взаимодействия</span><span class="sxs-lookup"><span data-stu-id="77c32-125">Interop Assemblies</span></span>  
 <span data-ttu-id="77c32-126">В следующей процедуре вы создадите сборку взаимодействия, который выступает в качестве моста между неуправляемым кодом (например, COM-объекта) и управляемым кодом, который использует Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="77c32-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="77c32-127">Сборки взаимодействия, который создает Visual Basic обрабатывает многие детали работы с объектами COM, такие как *маршалинг взаимодействия*, процесс упаковки параметров и возвращаемых значений в данных типов при переходе и из COM-объектов.</span><span class="sxs-lookup"><span data-stu-id="77c32-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="77c32-128">Ссылка на сборку взаимодействия, а не к самому объекту COM. в пунктах приложения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77c32-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="77c32-129">Для использования COM-объекта с помощью Visual Basic 2005 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="77c32-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1. <span data-ttu-id="77c32-130">Откройте новый проект приложения Windows на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77c32-130">Open a new Visual Basic Windows Application project.</span></span>  
  
2. <span data-ttu-id="77c32-131">В меню **Проект** щелкните команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="77c32-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="77c32-132">Появится диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="77c32-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3. <span data-ttu-id="77c32-133">На **COM** дважды щелкните `ComObject1` в **имя компонента** списке и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="77c32-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4. <span data-ttu-id="77c32-134">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="77c32-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="77c32-135">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="77c32-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5. <span data-ttu-id="77c32-136">В **шаблоны** панели щелкните **класс**.</span><span class="sxs-lookup"><span data-stu-id="77c32-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="77c32-137">Имя файла по умолчанию, `Class1.vb`, отображается в **имя** поля.</span><span class="sxs-lookup"><span data-stu-id="77c32-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="77c32-138">Это поле следует изменять MathClass.vb и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="77c32-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="77c32-139">Это создает класс с именем `MathClass`и отображает его код.</span><span class="sxs-lookup"><span data-stu-id="77c32-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6. <span data-ttu-id="77c32-140">Добавьте следующий код в верхнюю часть `MathClass` для наследования от класса COM.</span><span class="sxs-lookup"><span data-stu-id="77c32-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]  
  
7. <span data-ttu-id="77c32-141">Перегрузите открытый метод базового класса, добавив следующий код, чтобы `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="77c32-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]  
  
8. <span data-ttu-id="77c32-142">Расширить наследуемого класса, добавив следующий код, чтобы `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="77c32-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]  
  
 <span data-ttu-id="77c32-143">Новый класс наследует свойства базового класса в COM-объекта, перегружающий метод и определяет новый метод для расширения класса.</span><span class="sxs-lookup"><span data-stu-id="77c32-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="77c32-144">Чтобы проверить унаследованный класс</span><span class="sxs-lookup"><span data-stu-id="77c32-144">To test the inherited class</span></span>  
  
1. <span data-ttu-id="77c32-145">Добавьте кнопку в форму запуска и дважды щелкните его, чтобы просмотреть ее код.</span><span class="sxs-lookup"><span data-stu-id="77c32-145">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2. <span data-ttu-id="77c32-146">На кнопке панели `Click` процедуры обработчика событий, добавьте следующий код для создания экземпляра `MathClass` и вызова перегруженных методов:</span><span class="sxs-lookup"><span data-stu-id="77c32-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]  
  
3. <span data-ttu-id="77c32-147">Запустите проект, нажав клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="77c32-147">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="77c32-148">При нажатии кнопки в форме `AddNumbers` с первого вызова метода `Short` данных введите числа, и Visual Basic выбирает соответствующий метод из базового класса.</span><span class="sxs-lookup"><span data-stu-id="77c32-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="77c32-149">Второй вызов `AddNumbers` направляется в перегруженный метод `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="77c32-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="77c32-150">Третий вызов вызовы `SubtractNumbers` метод, который расширяет класс.</span><span class="sxs-lookup"><span data-stu-id="77c32-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="77c32-151">Свойству в базовом классе, а значение отображается.</span><span class="sxs-lookup"><span data-stu-id="77c32-151">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="77c32-152">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="77c32-152">Next Steps</span></span>  
 <span data-ttu-id="77c32-153">Вы могли заметить, перегруженных `AddNumbers` имеет тот же тип данных, метод, унаследованный от базового класса COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="77c32-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="77c32-154">Это обусловлено тем, аргументы и параметры метода базового класса определяются как 16-разрядных целых чисел в Visual Basic 6.0, но они представляются как 16-разрядных целых чисел типа `Short` в более поздних версиях Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77c32-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="77c32-155">Новая функция поддерживает 32-разрядных целых чисел и перегружает функцию базового класса.</span><span class="sxs-lookup"><span data-stu-id="77c32-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="77c32-156">При работе с COM-объектов, убедитесь, что проверить размер и типы данных параметров.</span><span class="sxs-lookup"><span data-stu-id="77c32-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="77c32-157">Например при использовании COM-объект, который принимает в качестве аргумента объект коллекции Visual Basic 6.0, невозможно использовать коллекцию в поздних версиях Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="77c32-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="77c32-158">Свойства и методы, унаследованные от COM-классов можно переопределить, это означает, что можно объявить локальное свойство или метод, который заменяет свойство или метод, унаследованный от базового класса COM.</span><span class="sxs-lookup"><span data-stu-id="77c32-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="77c32-159">Правила переопределения наследуемых свойств COM аналогичны правилам переопределения других свойств и методов, за исключением следующих случаев:</span><span class="sxs-lookup"><span data-stu-id="77c32-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="77c32-160">При переопределении свойства или методы, унаследованные от класса COM, необходимо переопределить все остальные унаследованные свойства и методы.</span><span class="sxs-lookup"><span data-stu-id="77c32-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="77c32-161">Свойства, использующие `ByRef` параметров не может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="77c32-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77c32-162">См. также</span><span class="sxs-lookup"><span data-stu-id="77c32-162">See also</span></span>

- [<span data-ttu-id="77c32-163">COM-взаимодействие в приложениях .NET Framework</span><span class="sxs-lookup"><span data-stu-id="77c32-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="77c32-164">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="77c32-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="77c32-165">Тип данных Short</span><span class="sxs-lookup"><span data-stu-id="77c32-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
