---
title: Общие сведения об элементе управления DomainUpDown
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745858"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Общие сведения об элементе управления DomainUpDown (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.DomainUpDown> представляет собой сочетание текстового поля и пары кнопок для перемещения вверх или вниз по списку. Элемент управления отображает и задает текстовую строку из списка вариантов. Пользователь может выбрать строку, нажимая кнопки вверх и вниз для перемещения по списку, нажимая клавиши со СТРЕЛКАми вверх и вниз или вводя строку, совпадающую с элементом в списке. Одним из возможных способов использования этого элемента управления является выбор элементов из списка имен, отсортированного по алфавиту.  
  
> [!NOTE]
> Чтобы отсортировать список, присвойте свойству <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> значение `true`.  
  
 Функция этого элемента управления очень похожа на список или поле со списком, но занимает немного пространства.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевыми свойствами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Свойство <xref:System.Windows.Forms.DomainUpDown.Items%2A> содержит список объектов, текстовые значения которых отображаются в элементе управления. Если <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> имеет значение `false`, элемент управления автоматически завершает текст, который пользователь вводит и сопоставляет со значением в списке. Если <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> имеет значение `true`, прокрутка после последнего элемента приведет к первому элементу в списке и наоборот. Ключевыми методами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Этот элемент управления отображает только текстовые строки. Если требуется элемент управления, отображающий числовые значения, используйте элемент управления <xref:System.Windows.Forms.NumericUpDown>. Дополнительные сведения см. в разделе [Общие сведения об элементе управления NumericUpDown](numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DomainUpDown>
- [Элемент управления DomainUpDown](domainupdown-control-windows-forms.md)
