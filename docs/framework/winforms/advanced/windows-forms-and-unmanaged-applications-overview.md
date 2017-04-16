---
title: "Общие сведения о Windows Forms и неуправляемых приложениях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "COM [Windows Forms]"
  - "Windows Forms, неуправляемые"
  - "взаимодействие COM"
  - "Элементы управления ActiveX [Windows Forms], об элементах управления ActiveX"
  - "Windows Forms, взаимодействие"
ms.assetid: 0a26d99d-8135-4895-8760-c9a2b5f67f14
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Общие сведения о Windows Forms и неуправляемых приложениях
Приложения и элементы управления Windows Forms могут взаимодействовать с неуправляемыми приложениями, но с некоторыми оговорками. В следующих разделах описываются сценарии и конфигурации, которые поддерживаются и не поддерживаются элементами управления и приложениями Windows Forms.  
  
## Элементы управления Windows Forms и приложения ActiveX  
 За исключением Microsoft Internet Explorer и Microsoft Foundation Classes \(MFC\), элементы управления Windows Forms не поддерживаются в приложениях, предназначенных для размещения элементов управления ActiveX. Другие приложения и средства разработки, способные размещать элементы управления ActiveX, включая контейнеры для тестирования ActiveX из версий Visual Studio, предшествующих Visual Studio .NET 2003, не поддерживают размещение элементов управления Windows Forms.  
  
 Эти ограничения также применимы к использованию элементов управления Windows Forms посредством COM\-взаимодействия. Использование элемента управления Windows Forms с помощью вызываемой оболочки COM \(CCW\) поддерживается только в Internet Explorer. Подробнее о COM\-взаимодействии см. в разделе  
  
 [COM\-взаимодействие](../Topic/COM%20Interop%20\(Visual%20Basic\).md).  
  
 В таблице ниже показаны доступные средства размещения ActiveX для элементов управления Windows Forms.  
  
|Версия Windows Forms|Поддержка|  
|--------------------------|---------------|  
|.NET Framework 1.0|Internet Explorer 5.01 и более поздние версии|  
|.NET Framework 1.1 и более поздние версии|Internet Explorer 5.01 и более поздние версии<br /><br /> Microsoft Foundation Classes \(MFC\) 7.0 и более поздние версии|  
  
## Размещение компонентов Windows Forms в качестве элементов управления ActiveX  
 В .NET Framework 1.1 поддержка была расширена для включения MFC 7.0 и более поздних версий. Эта поддержка включает в себя любой контейнер, полностью совместимый с MFC 7.0 или с более поздней версией контейнера элементов управления ActiveX.  
  
 Однако регистрация элементов управления Windows Forms как элементов управления ActiveX не поддерживается. Также не поддерживается вызов метода `com.ms.win32.Ole32.CoCreateInstance` для элементов управления Windows Forms. Поддерживается только управляемая активация элементов управления Windows Forms. После создания элемента управления Windows Forms его можно размещать в приложении MFC так же, как элемент управления ActiveX.  
  
 Чтобы использовать элементы управления Windows Forms в неуправляемом приложении, необходимо либо разместить среду CLR с помощью неуправляемых интерфейсов API размещения среды CLR, либо использовать возможности взаимодействия C\+\+. Рекомендуемым решением является использование возможностей взаимодействия C\+\+.  
  
## Windows Forms в клиентских приложениях COM  
 При открытии формы Windows Forms из клиентского приложения COM, такого как приложение Visual Basic 6.0 или приложение MFC, форма может вести себя не так, как ожидается. Например, при нажатии клавиши TAB фокус не переходит от одного элемента управления к другому. При нажатии клавиши ВВОД, если фокус установлен на кнопке, событие кнопки <xref:System.Windows.Forms.Control.Click> не возникает. Также может наблюдаться и другое неожиданное поведение при нажатии клавиш или действиях мышью.  
  
 Это происходит из\-за того, что неуправляемое приложение не реализует поддержку цикла обработки сообщений, которая необходима для правильной работы формы Windows Forms. Цикл обработки сообщений, реализуемый в клиентском приложении COM, существенно отличается от цикла обработки сообщений Windows Forms.  
  
 Цикл обработки сообщений приложения является внутренним циклом программы, который получает сообщения из очереди сообщений потока, преобразует их и отправляет приложению для обработки. Архитектура цикла обработки сообщений для формы Windows Forms отличается от архитектуры, используемой в более ранних приложениях, таких как приложения Visual Basic 6.0 и приложения MFC. Сообщения окна, которые отправляются в цикл обработки сообщений, могут обрабатываться не так, как ожидает форма Windows Forms. Таким образом, может наблюдаться неожиданное поведение. Могут не работать некоторые сочетания клавиш и некоторые действия мыши, а также могут не возникать некоторые события.  
  
## Устранение проблем взаимодействия  
 Эти проблемы можно устранить путем отображения формы в цикле обработки сообщений [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], который создается с помощью метода <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>.  
  
 Чтобы исправить работу формы Windows Forms из клиентского приложения COM, необходимо запустить его в цикле обработки сообщений Windows Forms. Для этого воспользуйтесь одним из перечисленных ниже подходов.  
  
-   Используйте метод <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName> для отображения Windows Form. Для получения дополнительной информации см. [Практическое руководство. Поддержка COM\-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Запускайте каждую форму Windows Forms в новом потоке. Для получения дополнительной информации см. [Практическое руководство. Поддержка COM\-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## См. также  
 [Windows Forms and Unmanaged Applications](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)   
 [COM\-взаимодействие](../Topic/COM%20Interop%20\(Visual%20Basic\).md)   
 [COM\-взаимодействие в приложениях .NET Framework](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md)   
 [COM Interoperability Samples](http://msdn.microsoft.com/ru-ru/09c38567-6380-4d70-848a-e896a4ca05f4)   
 [Aximp.exe \(Windows Forms ActiveX Control Importer\)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)   
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)   
 [Registering Assemblies with COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Практическое руководство. Поддержка COM\-взаимодействия путем отображения формы Windows Forms с помощью метода ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)   
 [Практическое руководство. Поддержка COM\-взаимодействия путем отображения каждой формы Windows Forms в отдельном потоке](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)