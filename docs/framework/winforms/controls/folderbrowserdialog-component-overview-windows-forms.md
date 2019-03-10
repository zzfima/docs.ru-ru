---
title: Общие сведения о компоненте FolderBrowserDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: d08eb456ea2d2d3b805d3df7e0e79b26ea7d415e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708253"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Общие сведения о компоненте FolderBrowserDialog (Windows Forms)
Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> компонент — это модальное диалоговое окно, которое используется для просмотра и выбора папки. Новые папки можно также создать изнутри <xref:System.Windows.Forms.FolderBrowserDialog> компонента.  
  
> [!NOTE]
>  Чтобы выбрать файлы, а не папки, используйте [OpenFileDialog](openfiledialog-component-windows-forms.md) компонента.  
  
 <xref:System.Windows.Forms.FolderBrowserDialog> Компонент отображается во время выполнения с помощью <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод. Задать <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> свойства, чтобы определить самую верхнюю папку и все вложенные папки, которые будут отображаться в представлении в виде дерева диалогового окна. После отображения диалоговое окно можно использовать <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> свойство, чтобы получить путь к папке, которая была выбрана.  
  
 При добавлении в форму, <xref:System.Windows.Forms.FolderBrowserDialog> компонент появится в области в нижней части конструктора Windows Forms.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Практическое руководство. Выберите папки с помощью компонента FolderBrowserDialog в Windows Forms](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [Компонент FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
