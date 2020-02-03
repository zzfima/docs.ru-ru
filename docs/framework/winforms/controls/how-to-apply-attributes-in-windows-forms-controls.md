---
title: Применение атрибутов в элементах управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: b8ecd516cf6bb189c6ad1b208dd8e3a5444f001c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741494"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="e1e36-102">Практическое руководство. Применение атрибутов к элементам управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e1e36-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="e1e36-103">Для разработки компонентов и элементов управления, которые правильно взаимодействуют со средой разработки и правильно выполняются во время выполнения, необходимо правильно применить атрибуты к классам и членам.</span><span class="sxs-lookup"><span data-stu-id="e1e36-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e36-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e1e36-104">Example</span></span>  
 <span data-ttu-id="e1e36-105">В следующем примере кода показано, как использовать несколько атрибутов для пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e1e36-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="e1e36-106">Элемент управления демонстрирует простую возможность ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="e1e36-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="e1e36-107">Когда элемент управления привязан к источнику данных, он отображает значения, отправленные источником данных в элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e1e36-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e1e36-108">Если значение превышает значение, заданное свойством `Threshold`, возникает событие `ThresholdExceeded`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="e1e36-109">`AttributesDemoControl` регистрирует значения с помощью класса `LogEntry`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="e1e36-110">Класс `LogEntry` является классом-шаблоном, что означает, что он параметризован для типа, который он записывает в журнал.</span><span class="sxs-lookup"><span data-stu-id="e1e36-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="e1e36-111">Например, если `AttributesDemoControl` ведет запись значений типа `float`, каждый экземпляр `LogEntry` объявляется и используется следующим образом.</span><span class="sxs-lookup"><span data-stu-id="e1e36-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="e1e36-112">Поскольку `LogEntry` параметризован произвольным типом, он должен использовать отражение для работы с типом параметра.</span><span class="sxs-lookup"><span data-stu-id="e1e36-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="e1e36-113">Чтобы функция порогового значения работала, тип параметра `T` должен реализовывать интерфейс <xref:System.IComparable>.</span><span class="sxs-lookup"><span data-stu-id="e1e36-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="e1e36-114">Форма, в которой размещается `AttributesDemoControl` периодически опрашивает счетчик производительности.</span><span class="sxs-lookup"><span data-stu-id="e1e36-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="e1e36-115">Каждое значение упаковывается в `LogEntry` соответствующего типа и добавляется в <xref:System.Windows.Forms.BindingSource>формы.</span><span class="sxs-lookup"><span data-stu-id="e1e36-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="e1e36-116">`AttributesDemoControl` получает значение через привязку данных и отображает значение в элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e1e36-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="e1e36-117">Первый пример кода является реализацией `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="e1e36-118">Во втором примере кода демонстрируется форма, использующая `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="e1e36-119">Атрибуты уровня класса</span><span class="sxs-lookup"><span data-stu-id="e1e36-119">Class-level Attributes</span></span>  
 <span data-ttu-id="e1e36-120">Некоторые атрибуты применяются на уровне класса.</span><span class="sxs-lookup"><span data-stu-id="e1e36-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="e1e36-121">В следующем примере кода показаны атрибуты, которые обычно применяются к элементу управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e1e36-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="e1e36-122">Атрибут TypeConverter</span><span class="sxs-lookup"><span data-stu-id="e1e36-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="e1e36-123"><xref:System.ComponentModel.TypeConverterAttribute> является другим часто используемым атрибутом уровня класса.</span><span class="sxs-lookup"><span data-stu-id="e1e36-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="e1e36-124">В следующем примере кода показано использование класса `LogEntry`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="e1e36-125">В этом примере также показана реализация <xref:System.ComponentModel.TypeConverter> для типа `LogEntry`, который называется `LogEntryTypeConverter`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="e1e36-126">Атрибуты уровня элемента</span><span class="sxs-lookup"><span data-stu-id="e1e36-126">Member-level Attributes</span></span>  
 <span data-ttu-id="e1e36-127">Некоторые атрибуты применяются на уровне элементов.</span><span class="sxs-lookup"><span data-stu-id="e1e36-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="e1e36-128">В следующих примерах кода показаны некоторые атрибуты, которые обычно применяются к свойствам элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e1e36-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="e1e36-129">Атрибут Амбиентвалуе</span><span class="sxs-lookup"><span data-stu-id="e1e36-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="e1e36-130">В следующем примере демонстрируется <xref:System.ComponentModel.AmbientValueAttribute> и демонстрируется код, который поддерживает взаимодействие с средой разработки.</span><span class="sxs-lookup"><span data-stu-id="e1e36-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="e1e36-131">Это взаимодействие называется *окружением*.</span><span class="sxs-lookup"><span data-stu-id="e1e36-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="e1e36-132">Атрибуты привязки данных</span><span class="sxs-lookup"><span data-stu-id="e1e36-132">Databinding Attributes</span></span>  
 <span data-ttu-id="e1e36-133">В следующих примерах демонстрируется реализация сложной привязки данных.</span><span class="sxs-lookup"><span data-stu-id="e1e36-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="e1e36-134"><xref:System.ComponentModel.ComplexBindingPropertiesAttribute>уровня класса, показанный ранее, указывает свойства `DataSource` и `DataMember`, используемые для привязки данных.</span><span class="sxs-lookup"><span data-stu-id="e1e36-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="e1e36-135"><xref:System.ComponentModel.AttributeProviderAttribute> указывает тип, к которому будет привязано свойство `DataSource`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1e36-136">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e1e36-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="e1e36-137">Для сборки в форме, в которой размещен `AttributesDemoControl`, требуется ссылка на сборку `AttributesDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="e1e36-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e36-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1e36-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="e1e36-139">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e1e36-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="e1e36-140">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e1e36-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="e1e36-141">[Последовательное руководство. Сериализация коллекций стандартных типов с помощью Десигнерсериализатионвисибилитяттрибуте](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e1e36-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
