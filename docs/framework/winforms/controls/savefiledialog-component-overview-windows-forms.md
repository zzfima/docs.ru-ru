---
title: Общие сведения о компоненте SaveFileDialog
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743099"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Общие сведения о компоненте SaveFileDialog (Windows Forms)

Компонент Windows Forms <xref:System.Windows.Forms.SaveFileDialog> является стандартным диалоговым окном. Это то же самое, что и стандартное диалоговое окно « **Сохранение файла** », используемое Windows. Он наследуется от класса <xref:System.Windows.Forms.CommonDialog>.

## <a name="working-with-the-savefiledialog-component"></a>Работа с компонентом SaveFileDialog

Используйте его как простое решение, позволяющее пользователям сохранять файлы вместо настройки собственного диалогового окна. Полагаться на стандартные диалоговые окна Windows, основные функциональные возможности создаваемых приложений будут сразу же знакомы пользователям. Однако имейте в виду, что при использовании компонента <xref:System.Windows.Forms.SaveFileDialog> необходимо написать собственную логику сохранения файлов.

Для вывода диалогового окна во время выполнения можно использовать метод <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>. Файл можно открыть в режиме чтения и записи с помощью метода <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>.

При добавлении в форму <xref:System.Windows.Forms.SaveFileDialog> компонент отображается в области в нижней части конструктор Windows Forms в Visual Studio.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.SaveFileDialog>
- [Компонент SaveFileDialog](savefiledialog-component-windows-forms.md)
