---
title: "Практическое руководство. Применение атрибутов к элементам управления Windows Forms | Microsoft Docs"
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
  - "атрибуты [Windows Forms], применение"
  - "элементы управления [Windows Forms], применение атрибутов"
  - "элементы управления Windows Forms, применение атрибутов"
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Применение атрибутов к элементам управления Windows Forms
Для разработки компонентов и элементов управления, которые правильно взаимодействуют со средой разработки и безошибочно выполняются во время выполнения, необходимо правильно применить атрибуты к классам и методам.  
  
## Пример  
 В представленном ниже примере кода демонстрируется использование нескольких атрибутов в пользовательском элементе управления.  Элемент управления демонстрирует простую возможность записи данных в журнал.  При связывании элемента управления с источником данных он отображает значения, отправленные источником данных в элемент управления <xref:System.Windows.Forms.DataGridView>.  Если значение превышает указанное в свойстве `Threshold`, инициируется событие `ThresholdExceeded`.  
  
 `AttributesDemoControl` записывает значения с классом `LogEntry`.  Класс `LogEntry` является классом шаблона, что означает, что он параметризован в типе, который он записывает.  Например, если `AttributesDemoControl` записывает значения типа `float`, каждый экземпляр `LogEntry` объявляется и используется следующим образом.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Так как `LogEntry` параметризован произвольным типом, он должен использовать отражение для работы в параметризованном типе.  Чтобы функция порогового значения работала, тип параметра `T` должен реализовать интерфейс <xref:System.IComparable>.  
  
 Форма с `AttributesDemoControl` периодически опрашивает счетчик производительности.  Каждое значение упаковывается в `LogEntry` соответствующего типа и добавляется в <xref:System.Windows.Forms.BindingSource> формы.  `AttributesDemoControl` получает значение через свою привязку данных и выводит значение в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Первый пример кода представляет реализацию `AttributesDemoControl`.  Второй пример кода демонстрирует форму с использованием `AttributesDemoControl`.  
  
## Атрибуты уровня классов  
 Некоторые атрибуты применяются на уровне класса.  В следующем примере кода показаны атрибуты, которые обычно применяются к элементу управления Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### Атрибут TypeConverter  
 <xref:System.ComponentModel.TypeConverterAttribute> является еще одним часто используемым атрибутом уровня класса.  В следующем примере кода показано его использование для класса `LogEntry`.  В этом примере также показана реализация <xref:System.ComponentModel.TypeConverter> для типа `LogEntry` с именем `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## Атрибуты уровня членов  
 Некоторые атрибуты применяются на уровне члена.  В следующих примерах кода показаны некоторые атрибуты, которые обычно применяются к свойствам элементов управления Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### Атрибут AmbientValue  
 Следующий пример демонстрирует <xref:System.ComponentModel.AmbientValueAttribute> и показывает код, поддерживающий взаимодействие со средой разработки.  Это взаимодействие называется *окружением*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### Атрибуты привязки данных  
 В следующих примерах демонстрируется реализация сложной привязки данных.  Атрибут уровня класса <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, показанный ранее, указывает свойства `DataSource` и `DataMember`, которые используются для привязки данных.  <xref:System.ComponentModel.AttributeProviderAttribute> указывает тип, к которому будет привязано свойство `DataSource`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## Компиляция кода  
  
-   Форма, содержащая `AttributesDemoControl`, требует ссылки на сборку `AttributesDemoControl` для построения.  
  
## См. также  
 <xref:System.IComparable>   
 <xref:System.Windows.Forms.DataGridView>   
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Атрибуты в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)