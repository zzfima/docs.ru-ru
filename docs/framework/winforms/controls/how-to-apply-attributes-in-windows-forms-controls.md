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
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Практическое руководство. Применение атрибутов к элементам управления Windows Forms
Для разработки компонентов и элементов управления, которые правильно взаимодействуют со средой разработки и правильно выполняются во время выполнения, необходимо правильно применить атрибуты к классам и членам.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как использовать несколько атрибутов для пользовательского элемента управления. Элемент управления демонстрирует простую возможность ведения журнала. Когда элемент управления привязан к источнику данных, он отображает значения, отправленные источником данных в элементе управления <xref:System.Windows.Forms.DataGridView>. Если значение превышает значение, заданное свойством `Threshold`, возникает событие `ThresholdExceeded`.  
  
 `AttributesDemoControl` регистрирует значения с помощью класса `LogEntry`. Класс `LogEntry` является классом-шаблоном, что означает, что он параметризован для типа, который он записывает в журнал. Например, если `AttributesDemoControl` ведет запись значений типа `float`, каждый экземпляр `LogEntry` объявляется и используется следующим образом.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> Поскольку `LogEntry` параметризован произвольным типом, он должен использовать отражение для работы с типом параметра. Чтобы функция порогового значения работала, тип параметра `T` должен реализовывать интерфейс <xref:System.IComparable>.  
  
 Форма, в которой размещается `AttributesDemoControl` периодически опрашивает счетчик производительности. Каждое значение упаковывается в `LogEntry` соответствующего типа и добавляется в <xref:System.Windows.Forms.BindingSource>формы. `AttributesDemoControl` получает значение через привязку данных и отображает значение в элементе управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Первый пример кода является реализацией `AttributesDemoControl`. Во втором примере кода демонстрируется форма, использующая `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Атрибуты уровня класса  
 Некоторые атрибуты применяются на уровне класса. В следующем примере кода показаны атрибуты, которые обычно применяются к элементу управления Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>Атрибут TypeConverter  
 <xref:System.ComponentModel.TypeConverterAttribute> является другим часто используемым атрибутом уровня класса. В следующем примере кода показано использование класса `LogEntry`. В этом примере также показана реализация <xref:System.ComponentModel.TypeConverter> для типа `LogEntry`, который называется `LogEntryTypeConverter`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a>Атрибуты уровня элемента  
 Некоторые атрибуты применяются на уровне элементов. В следующих примерах кода показаны некоторые атрибуты, которые обычно применяются к свойствам элементов управления Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a>Атрибут Амбиентвалуе  
 В следующем примере демонстрируется <xref:System.ComponentModel.AmbientValueAttribute> и демонстрируется код, который поддерживает взаимодействие с средой разработки. Это взаимодействие называется *окружением*.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a>Атрибуты привязки данных  
 В следующих примерах демонстрируется реализация сложной привязки данных. <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>уровня класса, показанный ранее, указывает свойства `DataSource` и `DataMember`, используемые для привязки данных. <xref:System.ComponentModel.AttributeProviderAttribute> указывает тип, к которому будет привязано свойство `DataSource`.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Для сборки в форме, в которой размещен `AttributesDemoControl`, требуется ссылка на сборку `AttributesDemoControl`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)
- [Атрибуты в элементах управления Windows Forms](attributes-in-windows-forms-controls.md)
- [Последовательное руководство. Сериализация коллекций стандартных типов с помощью Десигнерсериализатионвисибилитяттрибуте](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
