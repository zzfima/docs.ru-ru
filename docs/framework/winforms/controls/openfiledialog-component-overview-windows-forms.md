---
title: Общие сведения о компоненте OpenFileDialog (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: a49298b2e2cc620ad95e2e0b601a2f49f6ff79d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536082"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Общие сведения о компоненте OpenFileDialog (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.OpenFileDialog> является стандартным диалоговым окном. Он аналогичен **открыть файл** диалоговому операционной системы Windows. Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.  
  
## <a name="using-this-component"></a>С помощью данного компонента  
 Этот компонент используется в приложении Windows в качестве простого решения для выбора файлов вместо настройки собственного диалогового. Использование стандартных диалоговых окон Windows помогает создавать приложения, основные функциональные возможности которых хорошо знакомы пользователям. Имейте в виду, что при с помощью <xref:System.Windows.Forms.OpenFileDialog> компонента, необходимо написать свою собственную логику для открытия файла.  
  
 Используйте <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> метод для отображения диалогового окна во время выполнения. Можно разрешить пользователям выбрать несколько файлов, открываемых с <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> свойство. Кроме того, можно использовать <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> свойства, чтобы определить, если в диалоговом окне будет отображаться флажок только для чтения. <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Свойство указывает, будет ли установлен флажок только для чтения. Наконец <xref:System.Windows.Forms.FileDialog.Filter%2A> свойство задает текущий строку фильтра имен файлов, которая определяет варианты, которые отображаются в поле «Тип файлов» в диалоговом окне.  
  
 При добавлении в форму, <xref:System.Windows.Forms.OpenFileDialog> компонент появится в области в нижней части конструктора Windows Forms.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [Компонент OpenFileDialog](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
