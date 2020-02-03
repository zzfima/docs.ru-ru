---
title: Элемент управления DomainUpDown
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745836"
---
# <a name="domainupdown-control-windows-forms"></a>Элемент управления DomainUpDown (Windows Forms)
Элемент управления Windows Forms <xref:System.Windows.Forms.DomainUpDown> выглядит как сочетание текстового поля и пары кнопок для перемещения вверх или вниз по списку. Элемент управления отображает и задает текстовую строку из списка вариантов. Пользователь может выбрать строку, нажимая кнопки вверх и вниз для перемещения по списку, нажимая клавиши со СТРЕЛКАми вверх и вниз или вводя строку, совпадающую с элементом в списке. Одним из возможных способов использования этого элемента управления является выбор элементов из списка имен, отсортированного по алфавиту. (Чтобы отсортировать список, задайте для свойства <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> значение `true`.) Функция этого элемента управления очень похожа на список или поле со списком, но занимает немного пространства.  
  
 Ключевыми свойствами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.Items%2A>, <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A>и <xref:System.Windows.Forms.DomainUpDown.Wrap%2A>. Свойство <xref:System.Windows.Forms.DomainUpDown.Items%2A> содержит список объектов, текстовые значения которых отображаются в элементе управления. Если <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> имеет значение `false`, элемент управления автоматически завершает текст, который пользователь вводит и сопоставляет со значением в списке. Если <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> имеет значение `true`, прокрутка после последнего элемента приведет к первому элементу в списке и наоборот. Ключевыми методами элемента управления являются <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> и <xref:System.Windows.Forms.DomainUpDown.DownButton%2A>.  
  
 Этот элемент управления отображает только текстовые строки. Если требуется элемент управления, отображающий числовые значения, используйте элемент управления <xref:System.Windows.Forms.NumericUpDown>. Дополнительные сведения см. в разделе [элемент управления NumericUpDown](numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>в этом разделе  
 [Общие сведения об элементе управления DomainUpDown](domainupdown-control-overview-windows-forms.md)  
 Основные понятия, связанные с элементом управления <xref:System.Windows.Forms.DomainUpDown>, который позволяет пользователям просматривать список текстовых строк и выбирать их из списка.  
  
 [Практическое руководство. Добавление элементов в элемент управления DomainUpDown в Windows Forms](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Описывает, как указать текстовые строки, которые должен отображать элемент управления <xref:System.Windows.Forms.DomainUpDown>.  
  
 [Практическое руководство. Удаление элементов из элемента управления DomainUpDown в Windows Forms](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Описывает, как удалить элементы из элемента управления <xref:System.Windows.Forms.DomainUpDown> в коде.  
  
## <a name="reference"></a>Справочник  
 <xref:System.Windows.Forms.DomainUpDown>  
 Описание класса и всех его членов.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Описывает этот класс и содержит ссылки на все его члены.  
  
## <a name="related-sections"></a>См. также  
 [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md)  
 Полный список элементов управления Windows Forms со ссылками на информацию об их применении.
