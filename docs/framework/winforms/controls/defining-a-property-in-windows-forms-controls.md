---
title: Определение свойств элемента управления
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties [Windows Forms], defining in code
- custom controls [Windows Forms], defining properties in code
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
ms.openlocfilehash: 0fec817226a7da4b44ec992f9e384a2ad5449001
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746105"
---
# <a name="defining-a-property-in-windows-forms-controls"></a><span data-ttu-id="bc770-102">Определение свойства элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc770-102">Defining a Property in Windows Forms Controls</span></span>
<span data-ttu-id="bc770-103">Обзор свойств см. в разделе [Общие сведения о свойствах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="bc770-103">For an overview of properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="bc770-104">При определении свойства обратите внимание на приведенные ниже соображения:</span><span class="sxs-lookup"><span data-stu-id="bc770-104">There are a few important considerations when defining a property:</span></span>  
  
- <span data-ttu-id="bc770-105">К определяемым свойствам необходимо применять атрибуты.</span><span class="sxs-lookup"><span data-stu-id="bc770-105">You must apply attributes to the properties you define.</span></span> <span data-ttu-id="bc770-106">Атрибуты указывают, как конструктор должен отображать свойство.</span><span class="sxs-lookup"><span data-stu-id="bc770-106">Attributes specify how the designer should display a property.</span></span> <span data-ttu-id="bc770-107">Дополнительные сведения см. в разделе [Атрибуты времени разработки для компонентов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="bc770-107">For details, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
- <span data-ttu-id="bc770-108">Если изменение свойства влияет на визуальное отображение элемента управления, вызовите метод <xref:System.Windows.Forms.Control.Invalidate%2A> (элемент управления наследует от <xref:System.Windows.Forms.Control>) от метода доступа `set`.</span><span class="sxs-lookup"><span data-stu-id="bc770-108">If changing the property affects the visual display of the control, call the <xref:System.Windows.Forms.Control.Invalidate%2A> method (that your control inherits from <xref:System.Windows.Forms.Control>) from the `set` accessor.</span></span> <span data-ttu-id="bc770-109"><xref:System.Windows.Forms.Control.Invalidate%2A>, в свою очередь, вызывает метод <xref:System.Windows.Forms.Control.OnPaint%2A>, который перерисовывает элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bc770-109"><xref:System.Windows.Forms.Control.Invalidate%2A> in turn calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which redraws the control.</span></span> <span data-ttu-id="bc770-110">Несколько вызовов <xref:System.Windows.Forms.Control.Invalidate%2A> приводят к одному вызову <xref:System.Windows.Forms.Control.OnPaint%2A> для повышения эффективности.</span><span class="sxs-lookup"><span data-stu-id="bc770-110">Multiple calls to <xref:System.Windows.Forms.Control.Invalidate%2A> result in a single call to <xref:System.Windows.Forms.Control.OnPaint%2A> for efficiency.</span></span>  
  
- <span data-ttu-id="bc770-111">Библиотека классов .NET Framework предоставляет преобразователи типов для общих типов данных, таких как целые числа, десятичные числа, логические значения и прочие.</span><span class="sxs-lookup"><span data-stu-id="bc770-111">The .NET Framework class library provides type converters for common data types such as integers, decimal numbers, Boolean values, and others.</span></span> <span data-ttu-id="bc770-112">Преобразователь типов обычно предназначен для преобразования строки в значение (из строковых данных в данные другого типа).</span><span class="sxs-lookup"><span data-stu-id="bc770-112">The purpose of a type converter is generally to provide string-to-value conversion (from string data to other data types).</span></span> <span data-ttu-id="bc770-113">Общие типы данных связаны с преобразователями типов по умолчанию, которые преобразуют значения в строки, а строки — в соответствующие типы данных.</span><span class="sxs-lookup"><span data-stu-id="bc770-113">Common data types are associated with default type converters that convert values into strings and strings into the appropriate data types.</span></span> <span data-ttu-id="bc770-114">При определении свойства, являющегося пользовательским (то есть, нестандартным) типом данных необходимо применить атрибут, указывающий преобразователь типов для связи с этим свойством.</span><span class="sxs-lookup"><span data-stu-id="bc770-114">If you define a property that is a custom (that is, nonstandard) data type, you will have to apply an attribute that specifies the type converter to associate with that property.</span></span> <span data-ttu-id="bc770-115">Также можно использовать атрибут, чтобы связать пользовательский редактор типов пользовательского интерфейса со свойством.</span><span class="sxs-lookup"><span data-stu-id="bc770-115">You can also use an attribute to associate a custom UI type editor with a property.</span></span> <span data-ttu-id="bc770-116">Редактор типов пользовательского интерфейса предоставляет пользовательский интерфейс для редактирования свойства или типа данных.</span><span class="sxs-lookup"><span data-stu-id="bc770-116">A UI type editor provides a user interface for editing a property or data type.</span></span> <span data-ttu-id="bc770-117">Палитра — это пример редактора типов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bc770-117">A color picker is an example of a UI type editor.</span></span> <span data-ttu-id="bc770-118">Примеры атрибутов приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="bc770-118">Examples of attributes are given at the end of this topic.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="bc770-119">Если преобразователь типов или редактор типов пользовательского интерфейса недоступны для пользовательского свойства, можно реализовать один из них, как описано в разделе [Расширение поддержки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="bc770-119">If a type converter or a UI type editor is not available for your custom property, you can implement one as described in [Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120)).</span></span>  
  
 <span data-ttu-id="bc770-120">В следующем фрагменте кода определяется пользовательское свойство с именем `EndColor` для пользовательского элемента управления `FlashTrackBar`.</span><span class="sxs-lookup"><span data-stu-id="bc770-120">The following code fragment defines a custom property named `EndColor` for the custom control `FlashTrackBar`.</span></span>  
  
```vb  
Public Class FlashTrackBar  
   Inherits Control  
   ...  
   ' Private data member that backs the EndColor property.  
   Private _endColor As Color = Color.LimeGreen  
  
   ' The Category attribute tells the designer to display  
   ' it in the Flash grouping.   
   ' The Description attribute provides a description of  
   ' the property.   
   <Category("Flash"), _  
   Description("The ending color of the bar.")>  _  
   Public Property EndColor() As Color  
      ' The public property EndColor accesses _endColor.  
      Get  
         Return _endColor  
      End Get  
      Set  
         _endColor = value  
         If Not (baseBackground Is Nothing) And showGradient Then  
            baseBackground.Dispose()  
            baseBackground = Nothing  
         End If  
         ' The Invalidate method calls the OnPaint method, which redraws    
         ' the control.  
         Invalidate()  
      End Set  
   End Property  
   ...  
End Class  
```  
  
```csharp  
public class FlashTrackBar : Control {  
   ...  
   // Private data member that backs the EndColor property.  
   private Color endColor = Color.LimeGreen;  
   // The Category attribute tells the designer to display  
   // it in the Flash grouping.   
   // The Description attribute provides a description of  
   // the property.   
   [  
   Category("Flash"),  
   Description("The ending color of the bar.")  
   ]  
   // The public property EndColor accesses endColor.  
   public Color EndColor {  
      get {  
         return endColor;  
      }  
      set {  
         endColor = value;  
         if (baseBackground != null && showGradient) {  
            baseBackground.Dispose();  
            baseBackground = null;  
         }  
         // The Invalidate method calls the OnPaint method, which redraws   
         // the control.  
         Invalidate();  
      }  
   }  
   ...  
}  
```  
  
 <span data-ttu-id="bc770-121">В следующем фрагменте кода преобразователь типов и редактор типов пользовательского интерфейса связывается со свойством `Value`.</span><span class="sxs-lookup"><span data-stu-id="bc770-121">The following code fragment associates a type converter and a UI type editor with the property `Value`.</span></span> <span data-ttu-id="bc770-122">В этом случае `Value` является целым числом и имеет преобразователь типов по умолчанию, но атрибут <xref:System.ComponentModel.TypeConverterAttribute> применяет пользовательский преобразователь типов (`FlashTrackBarValueConverter`), который позволяет конструктору отображать его в процентах.</span><span class="sxs-lookup"><span data-stu-id="bc770-122">In this case `Value` is an integer and has a default type converter, but the <xref:System.ComponentModel.TypeConverterAttribute> attribute applies a custom type converter (`FlashTrackBarValueConverter`) that enables the designer to display it as a percentage.</span></span> <span data-ttu-id="bc770-123">Редактор типов пользовательского интерфейса, `FlashTrackBarValueEditor`, позволяет визуально отображать проценты.</span><span class="sxs-lookup"><span data-stu-id="bc770-123">The UI type editor, `FlashTrackBarValueEditor`, allows the percentage to be displayed visually.</span></span> <span data-ttu-id="bc770-124">В этом примере также показано, что преобразователь типов или редактор, заданный атрибутом <xref:System.ComponentModel.TypeConverterAttribute> или <xref:System.ComponentModel.EditorAttribute>, переопределяет преобразователь по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc770-124">This example also shows that the type converter or editor specified by the <xref:System.ComponentModel.TypeConverterAttribute> or <xref:System.ComponentModel.EditorAttribute> attribute overrides the default converter.</span></span>  
  
```vb  
<Category("Flash"), _  
TypeConverter(GetType(FlashTrackBarValueConverter)), _  
Editor(GetType(FlashTrackBarValueEditor), _  
GetType(UITypeEditor)), _  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")>  _  
Public ReadOnly Property Value() As Integer  
...  
End Property  
```  
  
```csharp  
[  
Category("Flash"),   
TypeConverter(typeof(FlashTrackBarValueConverter)),  
Editor(typeof(FlashTrackBarValueEditor), typeof(UITypeEditor)),  
Description("The current value of the track bar.  You can enter an actual value or a percentage.")  
]  
public int Value {  
...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc770-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="bc770-125">See also</span></span>

- [<span data-ttu-id="bc770-126">Свойства элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc770-126">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="bc770-127">Определение значений по умолчанию с помощью методов ShouldSerialize и Reset</span><span class="sxs-lookup"><span data-stu-id="bc770-127">Defining Default Values with the ShouldSerialize and Reset Methods</span></span>](defining-default-values-with-the-shouldserialize-and-reset-methods.md)
- [<span data-ttu-id="bc770-128">События изменения свойств</span><span class="sxs-lookup"><span data-stu-id="bc770-128">Property-Changed Events</span></span>](property-changed-events.md)
- [<span data-ttu-id="bc770-129">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc770-129">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
