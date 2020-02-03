---
title: Общие сведения о компоненте OpenFileDialog
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728434"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Общие сведения о компоненте OpenFileDialog (Windows Forms)

Компонент Windows Forms <xref:System.Windows.Forms.OpenFileDialog> является стандартным диалоговым окном. Это то же диалоговое окно **открытия файла** , которое предоставляется операционной системой Windows. Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.

## <a name="use-this-component"></a>Использовать этот компонент

Используйте этот компонент в приложении Windows в качестве простого решения для выбора файлов вместо настройки собственного диалогового окна. Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям. Однако имейте в виду, что при использовании компонента <xref:System.Windows.Forms.OpenFileDialog> необходимо написать собственную логику открытия файлов.

Используйте метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> для вывода диалогового окна во время выполнения. Можно разрешить пользователям выбирать несколько файлов для открытия с помощью свойства <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>. Кроме того, можно использовать свойство <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>, чтобы определить, отображается ли флажок только для чтения в диалоговом окне. Свойство <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> указывает, установлен ли флажок только для чтения. Наконец, свойство <xref:System.Windows.Forms.FileDialog.Filter%2A> задает текущую строку фильтра имен файлов, которая определяет варианты, отображаемые в поле "тип файлов" диалогового окна.

При добавлении в форму <xref:System.Windows.Forms.OpenFileDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.OpenFileDialog>
- [Компонент OpenFileDialog](openfiledialog-component-windows-forms.md)
