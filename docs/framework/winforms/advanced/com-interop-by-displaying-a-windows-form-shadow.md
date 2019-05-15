---
title: Практическое руководство. Обеспечение поддержки COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: f2fb48e07243694b14904b240bdcb0739175c2fc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593529"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Практическое руководство. Обеспечение поддержки COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog
Проблемы взаимодействия объектов модели компонентов (COM) можно устранить путем отображения формы Windows в цикл обработки сообщений .NET Framework, которые созданы с помощью <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> метод.  
  
 Чтобы исправить работу формы из клиентского приложения COM, необходимо запустить его в цикле сообщений Windows Forms. Для этого воспользуйтесь одним из перечисленных ниже подходов.  
  
- Используйте метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> для отображения формы Windows Forms.  
  
- Отображайте каждую форму Windows Forms в отдельном потоке. Дополнительные сведения см. в разделе [Практическое руководство. Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Процедура  
 С помощью <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> метод может быть самым простым способом отображения формы в цикле обработки сообщений .NET Framework, потому, что среди всех методов, он требует меньше всего кода.  
  
 Метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> приостанавливает цикл сообщений неуправляемого приложения и отображает форму в виде диалогового окна. Так как цикл обработки сообщений ведущего приложения приостановлен, <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> метод создает новый цикл обработки сообщений .NET Framework для обработки сообщений формы.  
  
 Недостатком использования метода <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> является то, что форма будет открыта как модальное диалоговое окно. Такое поведение блокирует любой пользовательский интерфейс в вызывающем приложении, пока открыта форма Windows Forms. Когда пользователь выходит из формы, цикл обработки сообщений .NET Framework закрывает и цикл обработки сообщений приложения снова начинает выполняться.  
  
 Можно создать библиотеку классов в Windows Forms, которая содержит метод для отображения формы, а затем выполнить сборку библиотеки классов для COM-взаимодействия. Можно использовать этот DLL-файл из Visual Basic 6.0 или Microsoft Foundation Classes (MFC) — вызвать метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> для отображения формы можно из любой из этих сред .  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Обеспечение поддержки COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog  
  
- Замените все вызовы <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> вызовы <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> метод в компоненте платформы .NET Framework.  
  
## <a name="see-also"></a>См. также

- [Предоставление компонентов .NET Framework клиентам COM](../../interop/exposing-dotnet-components-to-com.md)
- [Практическое руководство. Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows Forms и неуправляемые приложения](windows-forms-and-unmanaged-applications.md)
