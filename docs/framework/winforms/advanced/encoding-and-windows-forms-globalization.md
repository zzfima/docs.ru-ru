---
title: Кодировка и глобализация Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
ms.openlocfilehash: 60ca9f7ba2f716b5dab1b0276bc3cd07ddd8f65c
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736890"
---
# <a name="encoding-and-windows-forms-globalization"></a>Кодировка и глобализация Windows Forms

Приложения Windows Forms полностью поддерживают Юникод, т. е. каждый символ представлен уникальным числом независимо от платформы, программы или языка. Дополнительные сведения о юникоде см. на [веб-сайте консорциума Unicode](https://www.unicode.org).

## <a name="benefits-of-unicode"></a>Преимущества Юникода

В число преимуществ форм с поддержкой Юникода входит возможность работать с языками, поддерживаемыми только Юникодом, например хинди. Кроме того, можно работать с несколькими языками в одной форме. В Юникоде все символы занимают два байта, поэтому для представления двухбайтовых символов не требуется специальных усилий. Также можно написать единый код, который будет работать на всех платформах. Это отличие от предыдущих версий Visual Basic, в которых пришлось писать разные коды для различных платформ, таких как Windows NT и Windows 98.

Однако некоторые элементы управления не поддерживают Юникод в Windows 98 и Windows Millennium Edition. Все эти элементы управления, которые наследуют от общего элемента управления, обрабатывают данные с кодовыми страницами Windows как ANSI. Это такие элементы управления, как <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> и <xref:System.Windows.Forms.StatusBar>. Таким образом, невозможно отображать данные Юникода в этих элементах управления на перечисленных платформах. Например, нельзя отображать японские символы в английской операционной системе Windows 98.

В качестве альтернативы элементам управления <xref:System.Windows.Forms.ToolBar> и <xref:System.Windows.Forms.StatusBar> можно использовать элементы управления <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.StatusStrip>, поддерживающие Юникод. Чтобы добиться схожего внешнего вида элементов в приложении, используйте для отрисовки меню элемент управления <xref:System.Windows.Forms.MenuStrip> вместо <xref:System.Windows.Forms.MainMenu>. Подобно элементам <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.StatusStrip>, элемент <xref:System.Windows.Forms.MenuStrip> также может обрабатывать и отображать символы Юникода.

## <a name="see-also"></a>См. также

- [Глобализация Windows Forms приложений](globalizing-windows-forms.md)
