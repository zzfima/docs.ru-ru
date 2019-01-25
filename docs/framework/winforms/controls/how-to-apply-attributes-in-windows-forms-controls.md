---
title: Как выполнить Применение атрибутов в элементах управления Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 522c8b207b86608e3bbd9a5831a3adb5c6d6d430
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735160"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="ad983-102">Как выполнить Применение атрибутов в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad983-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="ad983-103">Для разработки компонентов и элементов управления, которые правильно взаимодействуют со средой разработки и правильно выполнять во время выполнения, необходимо правильно применять атрибуты к классам и членам.</span><span class="sxs-lookup"><span data-stu-id="ad983-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad983-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ad983-104">Example</span></span>  
 <span data-ttu-id="ad983-105">В следующем примере кода демонстрируется использование нескольких атрибутов в пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ad983-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="ad983-106">Элемент управления демонстрирует возможности простые операции ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="ad983-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="ad983-107">Когда элемент управления привязан к источнику данных, он отображает значения, отправленные источником данных в <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad983-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ad983-108">Если значение превышает значение, заданное параметром `Threshold` свойства `ThresholdExceeded` события.</span><span class="sxs-lookup"><span data-stu-id="ad983-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="ad983-109">`AttributesDemoControl` Записывает значения с `LogEntry` класса.</span><span class="sxs-lookup"><span data-stu-id="ad983-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="ad983-110">`LogEntry` Класс — это класс шаблона, который означает, что он параметризован в типе, который он входит в систему.</span><span class="sxs-lookup"><span data-stu-id="ad983-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="ad983-111">Например если `AttributesDemoControl` записывает значения типа `float`, каждая `LogEntry` экземпляра объявляется и используется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ad983-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  <span data-ttu-id="ad983-112">Так как `LogEntry` параметризован произвольным типом, он должен использовать отражение для работы с типом параметра.</span><span class="sxs-lookup"><span data-stu-id="ad983-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="ad983-113">Функция порогового значения для работы, тип параметра `T` должен реализовывать <xref:System.IComparable> интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ad983-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="ad983-114">Форма, содержащая `AttributesDemoControl` периодически опрашивает счетчик производительности.</span><span class="sxs-lookup"><span data-stu-id="ad983-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="ad983-115">Каждое значение упаковывается в `LogEntry` соответствующего типа и добавления в форму <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="ad983-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="ad983-116">`AttributesDemoControl` Получает значение через свою привязку данных и отображает значение в <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ad983-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="ad983-117">В первом примере кода — `AttributesDemoControl` реализации.</span><span class="sxs-lookup"><span data-stu-id="ad983-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="ad983-118">Во втором примере кода демонстрируется форму, которая использует `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="ad983-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="ad983-119">Атрибуты уровня класса</span><span class="sxs-lookup"><span data-stu-id="ad983-119">Class-level Attributes</span></span>  
 <span data-ttu-id="ad983-120">Некоторые атрибуты применяются на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="ad983-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="ad983-121">В следующем примере кода показаны атрибуты, которые обычно применяются к элементу управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ad983-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="ad983-122">Атрибут TypeConverter</span><span class="sxs-lookup"><span data-stu-id="ad983-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="ad983-123"><xref:System.ComponentModel.TypeConverterAttribute> является еще одним часто используемые атрибутом уровня класса.</span><span class="sxs-lookup"><span data-stu-id="ad983-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="ad983-124">В следующем примере кода показано его использование для `LogEntry` класса.</span><span class="sxs-lookup"><span data-stu-id="ad983-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="ad983-125">В этом примере также показана реализация <xref:System.ComponentModel.TypeConverter> для `LogEntry` тип с именем `LogEntryTypeConverter`.</span><span class="sxs-lookup"><span data-stu-id="ad983-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="ad983-126">Атрибуты на уровне элемента</span><span class="sxs-lookup"><span data-stu-id="ad983-126">Member-level Attributes</span></span>  
 <span data-ttu-id="ad983-127">Некоторые атрибуты применяются на уровне членов.</span><span class="sxs-lookup"><span data-stu-id="ad983-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="ad983-128">В следующих примерах кода некоторые атрибуты, которые обычно применяются к свойствам элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ad983-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="ad983-129">Атрибут AmbientValue</span><span class="sxs-lookup"><span data-stu-id="ad983-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="ad983-130">В следующем примере демонстрируется <xref:System.ComponentModel.AmbientValueAttribute> ; содержит код, поддерживающий взаимодействие со средой разработки.</span><span class="sxs-lookup"><span data-stu-id="ad983-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="ad983-131">Это взаимодействие называется *окружением*.</span><span class="sxs-lookup"><span data-stu-id="ad983-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="ad983-132">Атрибуты привязки данных</span><span class="sxs-lookup"><span data-stu-id="ad983-132">Databinding Attributes</span></span>  
 <span data-ttu-id="ad983-133">В следующих примерах показано реализацию сложную привязку данных.</span><span class="sxs-lookup"><span data-stu-id="ad983-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="ad983-134">Уровня класса <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, показанный ранее, указывает `DataSource` и `DataMember` свойства, используемые для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="ad983-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="ad983-135"><xref:System.ComponentModel.AttributeProviderAttribute> Указывает тип, к которому `DataSource` будет привязано свойство.</span><span class="sxs-lookup"><span data-stu-id="ad983-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad983-136">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="ad983-136">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ad983-137">Форма, содержащая `AttributesDemoControl` необходима ссылка на `AttributesDemoControl` сборки для сборки.</span><span class="sxs-lookup"><span data-stu-id="ad983-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad983-138">См. также</span><span class="sxs-lookup"><span data-stu-id="ad983-138">See also</span></span>
- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="ad983-139">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ad983-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="ad983-140">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad983-140">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)
- [<span data-ttu-id="ad983-141">Практическое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="ad983-141">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](https://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
