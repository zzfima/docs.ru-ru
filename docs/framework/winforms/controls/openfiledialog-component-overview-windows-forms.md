---
title: Общие сведения о компоненте OpenFileDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: 24327ded50ac927642e2687b40b1f10de9bdf41e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211702"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Общие сведения о компоненте OpenFileDialog (Windows Forms)

Компонент Windows Forms <xref:System.Windows.Forms.OpenFileDialog> является стандартным диалоговым окном. Он аналогичен **открыть файл** диалоговое окно, предоставляемые операционной системой Windows. Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.

## <a name="use-this-component"></a>Использовать этот компонент

Этот компонент используется в приложении Windows в качестве простого решения для выбора файлов вместо настройки собственного диалогового. Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям. Однако имейте в виду, что при с помощью <xref:System.Windows.Forms.OpenFileDialog> компонента, необходимо написать свою собственную логику для открытия файла.

Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод для отображения диалогового окна во время выполнения. Можно разрешить пользователям выбрать несколько файлов для открытия с <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> свойство. Кроме того, можно использовать <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> свойства, чтобы определить, если в диалоговом окне отображается флажок только для чтения. <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Свойство указывает, установлен ли флажок «только для чтения». Наконец <xref:System.Windows.Forms.FileDialog.Filter%2A> свойство задает текущий строку фильтра имен файлов, которая определяет варианты, которые отображаются в поле «Тип файлов» в диалоговом окне.

При добавлении в форму, <xref:System.Windows.Forms.OpenFileDialog> компонент появится в области в нижней части конструктора Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.OpenFileDialog>
- [Компонент OpenFileDialog](openfiledialog-component-windows-forms.md)
