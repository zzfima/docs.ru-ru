---
title: Практическое руководство. Применение атрибутов к элементам управления Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 273d32927582f4467a92cd3b8f87e699c1f167d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922787"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a>Практическое руководство. Применение атрибутов к элементам управления Windows Forms
Для разработки компонентов и элементов управления, которые правильно взаимодействуют со средой разработки и правильно выполняются во время выполнения, необходимо правильно применить атрибуты к классам и членам.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как использовать несколько атрибутов для пользовательского элемента управления. Элемент управления демонстрирует простую возможность ведения журнала. Когда элемент управления привязан к источнику данных, он отображает значения, отправленные источником данных в <xref:System.Windows.Forms.DataGridView> элементе управления. Если значение превышает значение `Threshold` `ThresholdExceeded` , заданное свойством, возникает событие.  
  
 Записывает значения в журнал `LogEntry` с помощью класса. `AttributesDemoControl` `LogEntry` Класс является классом шаблона, что означает, что он параметризован для типа, который он записывает в журнал. Например, если параметр `AttributesDemoControl` выполняет ведение журнала значений типа `float`, каждый `LogEntry` экземпляр объявляется и используется следующим образом.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> Поскольку `LogEntry` параметр параметризован произвольным типом, он должен использовать отражение для работы с типом параметра. Чтобы функция порогового значения работала, тип `T` параметра должен <xref:System.IComparable> реализовывать интерфейс.  
  
 Форма, в которой периодически `AttributesDemoControl` размещаются запросы счетчика производительности. Каждое значение упаковывается в `LogEntry` соответствующий тип и добавляется в <xref:System.Windows.Forms.BindingSource>форму. Объект `AttributesDemoControl` получает значение через привязку данных и отображает значение <xref:System.Windows.Forms.DataGridView> в элементе управления.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 Первый пример кода является `AttributesDemoControl` реализацией. Во втором примере кода демонстрируется форма, использующая `AttributesDemoControl`.  
  
## <a name="class-level-attributes"></a>Атрибуты уровня класса  
 Некоторые атрибуты применяются на уровне класса. В следующем примере кода показаны атрибуты, которые обычно применяются к элементу управления Windows Forms.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a>Атрибут TypeConverter  
 <xref:System.ComponentModel.TypeConverterAttribute>— Это еще один часто используемый атрибут уровня класса. В следующем примере кода показано его использование для `LogEntry` класса. В этом примере также показана реализация <xref:System.ComponentModel.TypeConverter> `LogEntry` для типа с именем `LogEntryTypeConverter`.  
  
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
 В следующих примерах демонстрируется реализация сложной привязки данных. На уровне <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>класса, показанном ранее, `DataSource` указываются свойства `DataMember` и, используемые для привязки данных. Указывает тип, к `DataSource` которому будет привязано свойство. <xref:System.ComponentModel.AttributeProviderAttribute>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Для создания формы, в `AttributesDemoControl` которой размещен объект, требуется `AttributesDemoControl` ссылка на сборку.  
  
## <a name="see-also"></a>См. также

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [Разработка пользовательских элементов управления Windows Forms в .NET Framework](developing-custom-windows-forms-controls.md)
- [Атрибуты в элементах управления Windows Forms](attributes-in-windows-forms-controls.md)
- [Практическое руководство. Сериализация коллекций стандартных типов с помощью Десигнерсериализатионвисибилитяттрибуте](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
