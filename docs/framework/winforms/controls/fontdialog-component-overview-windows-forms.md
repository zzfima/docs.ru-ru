---
title: "Общие сведения о компоненте FontDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b1e00fc074148ddd53885bafbb490a3e3868fc0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="fontdialog-component-overview-windows-forms"></a>Общие сведения о компоненте FontDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.FontDialog> компонент является стандартным диалоговым окном, то есть стандартные Windows **шрифта** диалоговым окном, используемым для предоставления шрифты, установленные в системе. Он используется в приложении Windows в качестве простого решения для выбора шрифтов вместо настройки собственного диалогового.  
  
 По умолчанию в диалоговом окне отображаются списки шрифт, начертание и размер. Установите флажки для эффектов, как зачеркивание и подчеркивание; раскрывающегося списка для скрипта; и пример того, как будет выглядеть шрифт. (Сценарий относится к другой символ скриптов, которые доступны для данного шрифта, например, иврит или японский.) Чтобы отобразить диалоговое окно шрифтов, вызовите <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод.  
  
## <a name="key-properties"></a>Основные свойства  
 Компонент содержит несколько свойств, определяющих его внешний вид. Свойства, задайте параметры диалогового окна, <xref:System.Windows.Forms.FontDialog.Font%2A> и <xref:System.Windows.Forms.FontDialog.Color%2A>. <xref:System.Windows.Forms.FontDialog.Font%2A> Свойство задает шрифт, стиль, размер, сценариев и эффектов; например, `Arial, 10pt, style=Italic, Strikeout`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FontDialog>  
 [Компонент FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-windows-forms.md)
