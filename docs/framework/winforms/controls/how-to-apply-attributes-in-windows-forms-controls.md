---
title: "Практическое руководство. Применение атрибутов к элементам управления Windows Forms"
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
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4697ef7a74916bcc7b922f265262a83b8f0316d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Практическое руководство. Применение атрибутов к элементам управления Windows Forms
Для разработки компонентов и элементов управления, которые правильно взаимодействуют со средой разработки и привести к неправильному выполнению во время выполнения, необходимо правильно применить атрибуты к классам и членам.  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется использование нескольких атрибутов в пользовательский элемент управления. Элемент управления демонстрирует возможность простого протоколирования. Если элемент управления привязан к источнику данных, он отображает значения, отправленные источником данных в <xref:System.Windows.Forms.DataGridView> элемента управления. Если значение превышает значение, заданное параметром `Threshold` свойства `ThresholdExceeded` события.  
  
 `AttributesDemoControl` Записывает значения с `LogEntry` класса. `LogEntry` Класс — это класс шаблона, поэтому он параметризован в типе, который он записывает. Например если `AttributesDemoControl` записывает значения типа `float`, каждая `LogEntry` экземпляр объявляется и используется следующим образом.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  Поскольку `LogEntry` параметризован произвольным типом, он должен использовать отражение для работы в типе параметра. Функция порогового значения для работы, тип параметра `T` необходимо реализовать <xref:System.IComparable> интерфейса.  
  
 Форма, содержащая `AttributesDemoControl` периодически опрашивает счетчик производительности. Каждое значение упаковывается в `LogEntry` соответствующего типа и добавления в форму <xref:System.Windows.Forms.BindingSource>. `AttributesDemoControl` Получает значение через свою привязку данных и отображает значение в <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Первый пример кода является `AttributesDemoControl` реализации. Во втором примере кода демонстрируется форму, которая использует `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Атрибуты уровня класса  
 Некоторые атрибуты применяются на уровне класса. В следующем примере кода показаны атрибуты, которые обычно применяются к элементу управления Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>Атрибут TypeConverter  
 <xref:System.ComponentModel.TypeConverterAttribute>являются другой часто используемые атрибуты уровня класса. В следующем примере кода показано его использование для `LogEntry` класса. В этом примере также показана реализация <xref:System.ComponentModel.TypeConverter> для `LogEntry` тип с именем `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Атрибуты уровня членов  
 Некоторые атрибуты применяются на уровне элементов. В следующих примерах кода некоторые атрибуты, которые обычно применяются к свойствам элементов управления Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Атрибут AmbientValue  
 В следующем примере демонстрируется <xref:System.ComponentModel.AmbientValueAttribute> приведен код, поддерживающий взаимодействие со средой разработки. Это взаимодействие называется *окружением*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Атрибуты привязки данных  
 В следующих примерах демонстрируется реализация сложной привязки данных. Уровня класса <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, показанной ранее, указывает `DataSource` и `DataMember` свойства, используемые для привязки данных. <xref:System.ComponentModel.AttributeProviderAttribute> Указывает тип, к которому `DataSource` будет привязано свойство.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Форма, содержащая `AttributesDemoControl` требуется ссылка на `AttributesDemoControl` сборки для сборки.  
  
## <a name="see-also"></a>См. также  
 <xref:System.IComparable>  
 <xref:System.Windows.Forms.DataGridView>  
 [Разработка пользовательских элементов управления Windows Forms в .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [Атрибуты в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 [Как: сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)
