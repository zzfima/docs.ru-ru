---
title: "Практическое руководство. Поддержка COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 415ffebbcf196a163932b1b83e32a6128f0bf1a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Практическое руководство. Поддержка COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog
Проблемы COM-взаимодействия можно устранить путем отображения формы Windows Forms в цикле сообщений [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], который создается с помощью метода <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>.  
  
 Чтобы исправить работу формы из клиентского приложения COM, необходимо запустить его в цикле сообщений Windows Forms. Для этого воспользуйтесь одним из перечисленных ниже подходов.  
  
-   Используйте метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> для отображения формы Windows Forms.  
  
-   Отображайте каждую форму Windows Forms в отдельном потоке. Дополнительные сведения см. в разделе [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Процедура  
 Использование метода <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> может оказаться самым простым способом для отображения формы в цикле сообщений [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], так как он требует меньше всего кода.  
  
 Метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> приостанавливает цикл сообщений неуправляемого приложения и отображает форму в виде диалогового окна. Поскольку цикл сообщений ведущего приложения приостановлен, метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> создает новый цикл сообщений [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для обработки сообщений формы.  
  
 Недостатком использования метода <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> является то, что форма будет открыта как модальное диалоговое окно. Такое поведение блокирует любой пользовательский интерфейс в вызывающем приложении, пока открыта форма Windows Forms. Когда пользователь выходит из формы, цикл сообщений [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] закрывается, и снова начинает выполняться более ранний цикл сообщений приложения.  
  
 Можно создать библиотеку классов в Windows Forms, которая содержит метод для отображения формы, а затем выполнить сборку библиотеки классов для COM-взаимодействия. Можно использовать этот DLL-файл из Visual Basic 6.0 или Microsoft Foundation Classes (MFC) — вызвать метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> для отображения формы можно из любой из этих сред .  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Обеспечение поддержки COM-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog  
  
-   В своем компоненте [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] замените все вызовы метода <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> на вызовы метода <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 [Предоставление компонентов .NET Framework клиентам COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Практическое руководство. Поддержка COM-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 [Windows Forms и неуправляемые приложения](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)
