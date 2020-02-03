---
title: Общие сведения о компоненте FolderBrowserDialog
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745725"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a>Общие сведения о компоненте FolderBrowserDialog (Windows Forms)

Компонент Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> является модальным диалоговым окном, используемым для обзора и выбора папок. Новые папки также можно создавать в компоненте <xref:System.Windows.Forms.FolderBrowserDialog>.

> [!NOTE]
> Для выбора файлов вместо папок используйте компонент [OpenFileDialog](openfiledialog-component-windows-forms.md) .

Компонент <xref:System.Windows.Forms.FolderBrowserDialog> отображается во время выполнения с помощью метода <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>. Задайте свойство <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>, чтобы определить самую верхнюю папку и все вложенные папки, которые будут отображаться в представлении в виде дерева диалогового окна. После отображения диалогового окна можно использовать свойство <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>, чтобы получить путь к выбранной папке.

При добавлении в форму <xref:System.Windows.Forms.FolderBrowserDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [Практическое руководство. Выбор папки с помощью компонента FolderBrowserDialog в Windows Forms](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [Компонент FolderBrowserDialog](folderbrowserdialog-component-windows-forms.md)
