---
title: Общие сведения об элементе управления DomainUpDown (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 6fda542204e2b41dd1d729d2b940c6f38a5812ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965302"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Общие сведения об элементе управления DomainUpDown (Windows Forms)
Элемент управления <xref:System.Windows.Forms.DomainUpDown> Windows Forms представляет собой сочетание текстового поля и пары кнопок для перемещения вверх или вниз по списку. Элемент управления отображает и задает текстовую строку из списка вариантов. Пользователь может выбрать строку, нажимая кнопки вверх и вниз для перемещения по списку, нажимая клавиши со СТРЕЛКАми вверх и вниз или вводя строку, совпадающую с элементом в списке. Одним из возможных способов использования этого элемента управления является выбор элементов из списка имен, отсортированного по алфавиту.  
  
> [!NOTE]
> Чтобы отсортировать список, присвойте <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> `true`свойству значение.  
  
 Функция этого элемента управления очень похожа на список или поле со списком, но занимает немного пространства.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевыми свойствами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. <xref:System.Windows.Forms.DomainUpDown.Items%2A> Свойство содержит список объектов, текстовые значения которых отображаются в элементе управления. Если <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> параметр имеет `false`значение, элемент управления автоматически завершает текст, который пользователь вводит и сопоставляет со значением в списке. <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> Если`true`задано значение, прокрутка после последнего элемента приведет к первому элементу в списке и наоборот. Ключевыми методами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Этот элемент управления отображает только текстовые строки. Если требуется элемент управления, отображающий числовые значения, используйте <xref:System.Windows.Forms.NumericUpDown> элемент управления. Дополнительные сведения см. в разделе [Общие сведения об элементе управления NumericUpDown](numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DomainUpDown>
- [Элемент управления DomainUpDown](domainupdown-control-windows-forms.md)
