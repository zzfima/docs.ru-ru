---
title: "Руководство: Разработка простого элемента управления форм Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da876ec74bf80d4329451a9bf125421731c7f9de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a><span data-ttu-id="34b7f-102">Руководство: Разработка простого элемента управления форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34b7f-102">How to: Develop a Simple Windows Forms Control</span></span>
<span data-ttu-id="34b7f-103">В этом разделе рассматриваются основные этапы создания пользовательского элемента управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="34b7f-103">This section walks you through the key steps for authoring a custom Windows Forms control.</span></span> <span data-ttu-id="34b7f-104">Простой элемент управления, разработанный в этом примере разрешает выравнивание его <xref:System.Windows.Forms.Control.Text%2A> значение изменяемого свойства.</span><span class="sxs-lookup"><span data-stu-id="34b7f-104">The simple control developed in this walkthrough allows the alignment of its <xref:System.Windows.Forms.Control.Text%2A> property to be changed.</span></span> <span data-ttu-id="34b7f-105">Он не вызывает и не обрабатывает события.</span><span class="sxs-lookup"><span data-stu-id="34b7f-105">It does not raise or handle events.</span></span>  
  
### <a name="to-create-a-simple-custom-control"></a><span data-ttu-id="34b7f-106">Создание простого пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="34b7f-106">To create a simple custom control</span></span>  
  
1.  <span data-ttu-id="34b7f-107">Определите класс, производный от класса <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34b7f-107">Define a class that derives from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control{}  
    ```  
  
2.  <span data-ttu-id="34b7f-108">Определите свойства.</span><span class="sxs-lookup"><span data-stu-id="34b7f-108">Define properties.</span></span> <span data-ttu-id="34b7f-109">(Вам не требуются для определения свойств, так как элемент управления наследует многие свойства от <xref:System.Windows.Forms.Control> класс, но большинство пользовательских элементов управления обычно определяются дополнительные свойства.) В следующем фрагменте кода определяется свойство с именем `TextAlignment` , `FirstControl` использует для форматирования значения <xref:System.Windows.Forms.Control.Text%2A> свойство унаследовано от <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="34b7f-109">(You are not required to define properties, because a control inherits many properties from the <xref:System.Windows.Forms.Control> class, but most custom controls generally do define additional properties.) The following code fragment defines a property named `TextAlignment` that `FirstControl` uses to format the display of the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="34b7f-110">Дополнительные сведения об определении свойств см. в разделе [Общие сведения о свойствах](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span><span class="sxs-lookup"><span data-stu-id="34b7f-110">For more information about defining properties, see [Properties Overview](http://msdn.microsoft.com/library/8f1a1ff1-0f05-40e0-bfdf-80de8fff7d52).</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     <span data-ttu-id="34b7f-111">Если задано свойство, которое изменяет визуальное представление элемента управления, необходимо вызвать <xref:System.Windows.Forms.Control.Invalidate%2A> метод необходимости перерисовки элемента управления.</span><span class="sxs-lookup"><span data-stu-id="34b7f-111">When you set a property that changes the visual display of the control, you must invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method to redraw the control.</span></span> <span data-ttu-id="34b7f-112"><xref:System.Windows.Forms.Control.Invalidate%2A>определен в базовом классе <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="34b7f-112"><xref:System.Windows.Forms.Control.Invalidate%2A> is defined in the base class <xref:System.Windows.Forms.Control>.</span></span>  
  
3.  <span data-ttu-id="34b7f-113">Переопределите защищенный <xref:System.Windows.Forms.Control.OnPaint%2A> метод наследуется от <xref:System.Windows.Forms.Control> для предоставления логики отрисовки для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="34b7f-113">Override the protected <xref:System.Windows.Forms.Control.OnPaint%2A> method inherited from <xref:System.Windows.Forms.Control> to provide rendering logic to your control.</span></span> <span data-ttu-id="34b7f-114">Если не следует переопределять <xref:System.Windows.Forms.Control.OnPaint%2A>, ваш элемент управления не сможет себя нарисовать.</span><span class="sxs-lookup"><span data-stu-id="34b7f-114">If you do not override <xref:System.Windows.Forms.Control.OnPaint%2A>, your control will not be able to draw itself.</span></span> <span data-ttu-id="34b7f-115">В следующем фрагменте кода <xref:System.Windows.Forms.Control.OnPaint%2A> метод выводит <xref:System.Windows.Forms.Control.Text%2A> свойство унаследовано от <xref:System.Windows.Forms.Control> с выравниванием, определяемым значением `alignmentValue` поля.</span><span class="sxs-lookup"><span data-stu-id="34b7f-115">In the following code fragment, the <xref:System.Windows.Forms.Control.OnPaint%2A> method displays the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control> with the alignment specified by the `alignmentValue` field.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4.  <span data-ttu-id="34b7f-116">Укажите атрибуты для своего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="34b7f-116">Provide attributes for your control.</span></span> <span data-ttu-id="34b7f-117">Атрибуты позволяют визуальному конструктору адекватно отображать ваш элемент управления, а также его свойства и события во время разработки.</span><span class="sxs-lookup"><span data-stu-id="34b7f-117">Attributes enable a visual designer to display your control and its properties and events appropriately at design time.</span></span> <span data-ttu-id="34b7f-118">Код в следующем фрагменте применяет атрибуты к свойству `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="34b7f-118">The following code fragment applies attributes to the `TextAlignment` property.</span></span> <span data-ttu-id="34b7f-119">В конструкторе, например Visual Studio <xref:System.ComponentModel.CategoryAttribute.Category%2A> атрибут (показано в приведенном фрагменте кода) позволяет свойству отображаться в логические категории.</span><span class="sxs-lookup"><span data-stu-id="34b7f-119">In a designer such as Visual Studio, the <xref:System.ComponentModel.CategoryAttribute.Category%2A> attribute (shown in the code fragment) causes the property to be displayed under a logical category.</span></span> <span data-ttu-id="34b7f-120"><xref:System.ComponentModel.DescriptionAttribute.Description%2A> Атрибут вызывает строку описания, отображаемый в нижней части **свойства** окна при `TextAlignment` выбрано свойство.</span><span class="sxs-lookup"><span data-stu-id="34b7f-120">The <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attribute causes a descriptive string to be displayed at the bottom of the **Properties** window when the `TextAlignment` property is selected.</span></span> <span data-ttu-id="34b7f-121">Дополнительные сведения об атрибутах см. в разделе [Атрибуты времени разработки для компонентов](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).</span><span class="sxs-lookup"><span data-stu-id="34b7f-121">For more information about attributes, see [Design-Time Attributes for Components](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3).</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5.  <span data-ttu-id="34b7f-122">(Необязательно.) Предоставьте элементу управления ресурсы.</span><span class="sxs-lookup"><span data-stu-id="34b7f-122">(optional) Provide resources for your control.</span></span> <span data-ttu-id="34b7f-123">Чтобы предоставить элементу управления ресурс, такой как растровое изображение, можно использовать параметр компилятора (`/res` для C#), позволяющий упаковать ресурсы с элементом управления.</span><span class="sxs-lookup"><span data-stu-id="34b7f-123">You can provide a resource, such as a bitmap, for your control by using a compiler option (`/res` for C#) to package resources with your control.</span></span> <span data-ttu-id="34b7f-124">Во время выполнения ресурса можно получить с помощью методов <xref:System.Resources.ResourceManager> класса.</span><span class="sxs-lookup"><span data-stu-id="34b7f-124">At run time, the resource can be retrieved using the methods of the <xref:System.Resources.ResourceManager> class.</span></span> <span data-ttu-id="34b7f-125">Более подробную информацию о создании и использовании ресурсов см. в разделе [Ресурсы в приложениях для настольных систем](../../../../docs/framework/resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="34b7f-125">For more information about creating and using resources, see the [Resources in Desktop Apps](../../../../docs/framework/resources/index.md).</span></span>  
  
6.  <span data-ttu-id="34b7f-126">Скомпилируйте и разверните элемент управления.</span><span class="sxs-lookup"><span data-stu-id="34b7f-126">Compile and deploy your control.</span></span> <span data-ttu-id="34b7f-127">Чтобы скомпилировать и развернуть `FirstControl,`, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="34b7f-127">To compile and deploy `FirstControl,` execute the following steps:</span></span>  
  
    1.  <span data-ttu-id="34b7f-128">Сохраните код из представленного ниже примера в исходный файл (например, FirstControl.cs или FirstControl.vb).</span><span class="sxs-lookup"><span data-stu-id="34b7f-128">Save the code in the following sample to a source file (such as FirstControl.cs or FirstControl.vb).</span></span>  
  
    2.  <span data-ttu-id="34b7f-129">Скомпилируйте исходный код в сборку и сохраните его в каталог приложения.</span><span class="sxs-lookup"><span data-stu-id="34b7f-129">Compile the source code into an assembly and save it in your application's directory.</span></span> <span data-ttu-id="34b7f-130">Для этого выполните следующую команду из каталога, содержащего исходный файл.</span><span class="sxs-lookup"><span data-stu-id="34b7f-130">To accomplish this, execute the following command from the directory that contains the source file.</span></span>  
  
        ```vb  
        vbc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```csharp  
        csc /t:library /out:[path to your application's directory]/CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll FirstControl.cs  
        ```  
  
         <span data-ttu-id="34b7f-131">Параметр компилятора `/t:library` сообщает компилятору, что создаваемая сборка является библиотекой (а не исполняемым файлом).</span><span class="sxs-lookup"><span data-stu-id="34b7f-131">The `/t:library` compiler option tells the compiler that the assembly you are creating is a library (and not an executable).</span></span> <span data-ttu-id="34b7f-132">Параметр `/out` определяет путь и имя сборки.</span><span class="sxs-lookup"><span data-stu-id="34b7f-132">The `/out` option specifies the path and name of the assembly.</span></span> <span data-ttu-id="34b7f-133">Параметр `/r` определяет имена сборок, на которые ссылается код.</span><span class="sxs-lookup"><span data-stu-id="34b7f-133">The`/r` option provides the name of the assemblies that are referenced by your code.</span></span> <span data-ttu-id="34b7f-134">В этом примере создается закрытая сборка, которую могут использовать только ваши приложения.</span><span class="sxs-lookup"><span data-stu-id="34b7f-134">In this example, you create a private assembly that only your applications can use.</span></span> <span data-ttu-id="34b7f-135">Это значит, что сохранить ее в каталог приложения нельзя.</span><span class="sxs-lookup"><span data-stu-id="34b7f-135">Hence, you have to save it in your application's directory.</span></span> <span data-ttu-id="34b7f-136">Дополнительные сведения об упаковке и развертывании элемента управления, который нужно распределить, см. в разделе [Развертывание](../../../../docs/framework/deployment/index.md).</span><span class="sxs-lookup"><span data-stu-id="34b7f-136">For more information about packaging and deploying a control for distribution, see [Deployment](../../../../docs/framework/deployment/index.md).</span></span>  
  
 <span data-ttu-id="34b7f-137">В следующем примере показан код для `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="34b7f-137">The following sample shows the code for `FirstControl`.</span></span> <span data-ttu-id="34b7f-138">Элемент управления помещается в пространство имен `CustomWinControls`.</span><span class="sxs-lookup"><span data-stu-id="34b7f-138">The control is enclosed in the namespace `CustomWinControls`.</span></span> <span data-ttu-id="34b7f-139">Это пространство имен обеспечивает логическое группирование связанных типов.</span><span class="sxs-lookup"><span data-stu-id="34b7f-139">A namespace provides a logical grouping of related types.</span></span> <span data-ttu-id="34b7f-140">Элемент управления можно создавать в новом или в уже существующем пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="34b7f-140">You can create your control in a new or existing namespace.</span></span> <span data-ttu-id="34b7f-141">В C# объявление `using` (в Visual Basic `Imports`) обеспечивает доступ к типам из пространства имен без использования полного имени типа.</span><span class="sxs-lookup"><span data-stu-id="34b7f-141">In C#, the `using` declaration (in Visual Basic, `Imports`) allows types to be accessed from a namespace without using the fully qualified name of the type.</span></span> <span data-ttu-id="34b7f-142">В следующем примере `using` объявление позволяет коду доступ к классу <xref:System.Windows.Forms.Control> из <xref:System.Windows.Forms?displayProperty=nameWithType> просто <xref:System.Windows.Forms.Control> вместо того чтобы использовать полное доменное имя <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34b7f-142">In the following example, the `using` declaration allows code to access the class <xref:System.Windows.Forms.Control> from <xref:System.Windows.Forms?displayProperty=nameWithType> as simply <xref:System.Windows.Forms.Control> instead of having to use the fully qualified name <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## <a name="using-the-custom-control-on-a-form"></a><span data-ttu-id="34b7f-143">Использование пользовательского элемента управления в форме</span><span class="sxs-lookup"><span data-stu-id="34b7f-143">Using the Custom Control on a Form</span></span>  
 <span data-ttu-id="34b7f-144">В следующем примере показана простая форма с использованием `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="34b7f-144">The following example shows a simple form that uses `FirstControl`.</span></span> <span data-ttu-id="34b7f-145">Она создает три экземпляра `FirstControl` с разными значениями свойства `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="34b7f-145">It creates three instances of `FirstControl`, each with a different value for the `TextAlignment` property.</span></span>  
  
#### <a name="to-compile-and-run-this-sample"></a><span data-ttu-id="34b7f-146">Компиляция и выполнение примера</span><span class="sxs-lookup"><span data-stu-id="34b7f-146">To compile and run this sample</span></span>  
  
1.  <span data-ttu-id="34b7f-147">Сохраните код в следующем примере в исходный файл (SimpleForm.cs или SimpleForms.vb).</span><span class="sxs-lookup"><span data-stu-id="34b7f-147">Save the code in the following example to a source file (SimpleForm.cs or SimpleForms.vb).</span></span>  
  
2.  <span data-ttu-id="34b7f-148">Скомпилируйте исходный код в исполняемую сборку, выполнив следующую команду из каталога, содержащего исходный файл.</span><span class="sxs-lookup"><span data-stu-id="34b7f-148">Compile the source code into an executable assembly by executing the following command from the directory that contains the source file.</span></span>  
  
    ```vb  
    vbc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```csharp  
    csc /r:CustomWinControls.dll /r:System.dll /r:System.Windows.Forms.dll /r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     <span data-ttu-id="34b7f-149">CustomWinControls.dll — это сборка, которая содержит класс `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="34b7f-149">CustomWinControls.dll is the assembly that contains the class `FirstControl`.</span></span> <span data-ttu-id="34b7f-150">Эта сборка должна находиться в том же каталоге, что и исходный файл для формы, которая к ней обращается (SimpleForm.cs или SimpleForms.vb).</span><span class="sxs-lookup"><span data-stu-id="34b7f-150">This assembly must be in the same directory as the source file for the form that accesses it (SimpleForm.cs or SimpleForms.vb).</span></span>  
  
3.  <span data-ttu-id="34b7f-151">Выполните файла SimpleForm.exe с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="34b7f-151">Execute SimpleForm.exe using the following command.</span></span>  
  
    ```  
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="34b7f-152">См. также</span><span class="sxs-lookup"><span data-stu-id="34b7f-152">See Also</span></span>  
 [<span data-ttu-id="34b7f-153">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34b7f-153">Properties in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)  
 [<span data-ttu-id="34b7f-154">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34b7f-154">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)
