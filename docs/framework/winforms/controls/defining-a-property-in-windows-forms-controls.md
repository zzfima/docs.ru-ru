---
title: "Определение свойства элемента управления Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "пользовательские элементы управления [Windows Forms], определение свойств в программном коде"
  - "свойства [Windows Forms], определение в коде"
ms.assetid: c2eb8277-a842-4d99-89a9-647b901a0434
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Определение свойства элемента управления Windows Forms
Обзор свойств см. в разделе [Properties Overview](../Topic/Properties%20Overview.md).  Есть несколько важных требований для определения свойства.  
  
-   Необходимо применять атрибуты для определяемых свойств.  Атрибуты указывают, как конструктор должен отображать свойство.  Дополнительные сведения см. в разделе [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md).  
  
-   Если изменение свойства влияет на визуальное отображение элемента управления, вызовите метод <xref:System.Windows.Forms.Control.Invalidate%2A> \(его элемент управления наследует от <xref:System.Windows.Forms.Control>\) из метода доступа `set`.  <xref:System.Windows.Forms.Control.Invalidate%2A> в свою очередь вызовет метод <xref:System.Windows.Forms.Control.OnPaint%2A>, который обновит элемент управления.  Несколько вызовов <xref:System.Windows.Forms.Control.OnPaint%2A> по эффективности соответствуют одному вызову <xref:System.Windows.Forms.Control.Invalidate%2A>.  
  
-   Библиотека классов .NET Framework предоставляет преобразователи типов для основных типов данных, таких как целые и десятичные числа, логические значения и другие.  Целью преобразователей типов обычно является предоставление преобразования строки в значение \(из строковых данных в другие типы данных\).  Основные типы данных связаны с преобразователями типов по умолчанию, которые преобразуют значения в строки и строки — в соответствующие типы данных.  Если определяется свойство, являющееся пользовательским \(нестандартным\) типом данных, необходимо применить атрибут, указывающий преобразователь типов для связи с этим свойством.  Можно также использовать атрибут, чтобы связать пользовательский редактор типов пользовательского интерфейса со свойством.  Редактор типов пользовательского интерфейса предоставляет пользовательский интерфейс для изменения свойства или типа данных.  Палитра — пример редактора типов пользовательского интерфейса.  Примеры атрибутов даны в конце этого раздела.  
  
    > [!NOTE]
    >  Если преобразователь типов или редактор типов пользовательского интерфейса недоступны для пользовательского свойства, для их реализации можно воспользоваться способом, представленным в разделе [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)  
  
 Следующий фрагмент кода определяет пользовательское свойство с именем `EndColor` для пользовательского элемента управления `FlashTrackBar`.  
  
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
  
 Следующий фрагмент кода связывает преобразователь типов и редактор типов пользовательского интерфейса со свойством `Value`.  В данном случае `Value` — целое число, имеющее преобразователь типов по умолчанию, но атрибут <xref:System.ComponentModel.TypeConverterAttribute> применяет пользовательский преобразователь типов \(`FlashTrackBarValueConverter`\), который позволяет конструктору отображать его в виде процентного отношения.  Редактор типов пользовательского интерфейса `FlashTrackBarValueEditor` разрешает визуальное отображение процентного отношения.  Этот пример также показывает, что преобразователь типов или редактор, заданный атрибутами <xref:System.ComponentModel.TypeConverterAttribute> или <xref:System.ComponentModel.EditorAttribute>, переопределяет преобразователь по умолчанию.  
  
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
  
## См. также  
 [Свойства элементов управления Windows Forms](../../../../docs/framework/winforms/controls/properties-in-windows-forms-controls.md)   
 [Определение значений по умолчанию с помощью методов ShouldSerialize и Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)   
 [События изменения свойств](../../../../docs/framework/winforms/controls/property-changed-events.md)   
 [Атрибуты в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)