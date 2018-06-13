---
title: Общие сведения о компоненте PageSetupDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PageSetupDialog
helpviewer_keywords:
- Page Setup dialog box [Windows Forms], displaying
- PageSetupDialog component
ms.assetid: 791caacb-a5ca-4fca-bad9-1a5721ad697c
ms.openlocfilehash: 4e7b4548f5a178ed7b819dbc2edc37bb95e3e0f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534229"
---
# <a name="pagesetupdialog-component-overview-windows-forms"></a>Общие сведения о компоненте PageSetupDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.PageSetupDialog> компонент является предварительно настроенным диалоговым окном, используемым для задания сведений о странице для печати в приложениях Windows. Он используется в приложении Windows в качестве простого решения для задания параметров настройки страницы вместо настройки собственного диалогового. Можно разрешить пользователям задавать границ и полей, верхние и нижние колонтитулы и книжной и альбомной ориентации. Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям.  
  
## <a name="key-properties-and-methods"></a>Ключевые свойства и методы  
 Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод для отображения диалогового окна во время выполнения. Этот компонент имеет свойства, можно задать, которые связаны с либо одной странице (<xref:System.Drawing.Printing.PrintDocument> класс) или любой документ (<xref:System.Drawing.Printing.PageSettings> класса). Кроме того <xref:System.Windows.Forms.PageSetupDialog> компонент может использоваться для определения параметров определенного принтера, которые хранятся в <xref:System.Drawing.Printing.PrinterSettings> класса.  
  
 При добавлении в форму, <xref:System.Windows.Forms.PageSetupDialog> компонент появится в области в нижней части конструктора Windows Forms.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [Компонент PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
