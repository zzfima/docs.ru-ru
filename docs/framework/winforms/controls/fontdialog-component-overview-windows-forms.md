---
title: Общие сведения о компоненте FontDialog
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745702"
---
# <a name="fontdialog-component-overview-windows-forms"></a>Общие сведения о компоненте FontDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.FontDialog> является предварительно настроенным диалоговым окном, которое является стандартным диалоговым окном Windows **Font** , используемым для предоставления шрифтов, установленных в данный момент в системе. Используйте его в приложении Windows в качестве простого решения для выбора шрифта вместо настройки собственного диалогового окна.  
  
 По умолчанию в диалоговом окне отображаются списки для шрифта, стиля и размера шрифта. флажки для таких эффектов, как зачеркивание и подчеркивание; раскрывающийся список для скрипта; и пример того, как будет выглядеть шрифт. (Скрипт ссылается на различные символьные скрипты, доступные для данного шрифта, например иврит или японский.) Чтобы отобразить диалоговое окно Шрифт, вызовите метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Компонент имеет ряд свойств, которые настраивают его внешний вид. Свойства, заданные для выбора диалогового окна, <xref:System.Windows.Forms.FontDialog.Font%2A> и <xref:System.Windows.Forms.FontDialog.Color%2A>. Свойство <xref:System.Windows.Forms.FontDialog.Font%2A> задает шрифт, стиль, размер, скрипт и эффекты. Например, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.FontDialog>
- [Компонент FontDialog](fontdialog-component-windows-forms.md)
