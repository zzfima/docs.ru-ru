---
title: "Общие сведения о компоненте PrintDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDialog
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], about PrintDialog component
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b90d94165de6985b43d47809ae57bfcae204f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="printdialog-component-overview-windows-forms"></a>Общие сведения о компоненте PrintDialog (Windows Forms)
Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) компонент является стандартным диалоговым окном, используемый для выбора принтера, печатаемых страниц и определения других параметров печати в приложениях Windows. Он используется в качестве простого решения для выбора принтера и параметров печати вместо самостоятельной настройки диалогового окна. Можно разрешить пользователям печатать много частей документов: печать всех, указанного диапазона страниц или выделенного фрагмента текста. Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям. <xref:System.Windows.Forms.PrintDialog> Компонент наследуется от <xref:System.Windows.Forms.CommonDialog> класса.  
  
## <a name="working-with-the-component"></a>Работа с компонентом  
 Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод, чтобы отобразить диалоговое окно во время выполнения. Этот компонент имеет свойства, относящиеся либо заданиях (<xref:System.Drawing.Printing.PrintDocument> класс) или параметры отдельных принтера (<xref:System.Drawing.Printing.PrinterSettings> класса). Любой из этих, в свою очередь, могут совместно использоваться несколькими принтерами.  
  
 При добавлении в форму, <xref:System.Windows.Forms.PrintDialog> компонент появится в области в нижней части конструктора Windows Forms.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.PrintDialog>  
 [Компонент PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)
