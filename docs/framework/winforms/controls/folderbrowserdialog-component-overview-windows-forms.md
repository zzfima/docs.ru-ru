---
title: "Общие сведения о компоненте FolderBrowserDialog (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7fab1dbe01c5b21e510841b1541150f6152ab0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Общие сведения о компоненте FolderBrowserDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> компонент является модальным диалоговым окном, который используется для просмотра и выбора папки. Новые папки могут также создаваться внутри <xref:System.Windows.Forms.FolderBrowserDialog> компонента.  
  
> [!NOTE]
>  Чтобы выбрать файлы, вместо папки, используйте [OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md) компонента.  
  
 <xref:System.Windows.Forms.FolderBrowserDialog> Компонент отображается во время выполнения с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод. Задать <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> свойства, чтобы определить папку верхнего уровня и все вложенные папки, которые будут отображаться в представлении дерева в диалоговом окне. После отображения диалоговое окно можно использовать <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> свойства, чтобы получить путь к папке, которая была выбрана.  
  
 При добавлении в форму, <xref:System.Windows.Forms.FolderBrowserDialog> компонент появится в области в нижней части конструктора Windows Forms.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.FolderBrowserDialog>  
 [Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms](../../../../docs/framework/winforms/controls/how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)  
 [Компонент FolderBrowserDialog](../../../../docs/framework/winforms/controls/folderbrowserdialog-component-windows-forms.md)
