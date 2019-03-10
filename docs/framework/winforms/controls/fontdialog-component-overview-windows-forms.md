---
title: Общие сведения о компоненте FontDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 26bfb561c1050438b78c4ae0a3e6e8da32458cdd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725042"
---
# <a name="fontdialog-component-overview-windows-forms"></a>Общие сведения о компоненте FontDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.FontDialog> компонент является стандартным диалоговым окном, который является стандартной Windows **шрифта** диалоговое окно, используемое для предоставления шрифтов, установленных в системе. Используйте его в приложении Windows в качестве простого решения для выбора шрифтов, вместо настройки собственного диалогового окна.  
  
 По умолчанию в диалоговом окне отображаются списки с множественным для шрифта, стиль шрифта и размера; Установите флажки для эффектов, как зачеркивание и подчеркивание; стрелку раскрывающегося списка для скрипта; и пример того, как будет выглядеть шрифт. (Сценарий ссылается на другой символ сценарии, которые доступны для данного шрифта, к примеру, иврит или японский.) Чтобы отобразить диалоговое окно "Шрифт", вызовите <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Компонент содержит ряд свойств, определяющих его внешний вид. Свойства, задайте параметры диалогового окна, <xref:System.Windows.Forms.FontDialog.Font%2A> и <xref:System.Windows.Forms.FontDialog.Color%2A>. <xref:System.Windows.Forms.FontDialog.Font%2A> Задает свойства шрифта, стиль, размер, скрипт и эффектов; например, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.FontDialog>
- [Компонент FontDialog](fontdialog-component-windows-forms.md)
