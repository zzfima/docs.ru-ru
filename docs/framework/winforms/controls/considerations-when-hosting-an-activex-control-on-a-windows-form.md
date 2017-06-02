---
title: "Вопросы размещения элемента управления ActiveX в форме Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления ActiveX [Windows Forms], добавление"
  - "элементы управления ActiveX [Windows Forms], размещение"
  - "элементы управления Windows Forms, элементы управления ActiveX"
  - "Windows Forms, элементы управления ActiveX"
  - "Windows Forms, размещение элементов управления ActiveX"
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Вопросы размещения элемента управления ActiveX в форме Windows Forms
Несмотря на то, что Windows Forms оптимизированы для работы с элементами управления Windows Forms, можно также использовать элементы управления ActiveX.  Ниже приведены вопросы, о которых следует помнить при планировании приложения, использующего элементы управления ActiveX.  
  
-   **Безопасность** Общеязыковая среда выполнения была усовершенствована в отношении управления доступом для кода.  Приложения, использующие Windows Forms, могут без проблем запускаться в полностью доверенных средах и, сохраняя большинство функциональных возможностей, — в частично доверенных средах.  Элементы управления Windows Forms легко воспринимаются браузером.  Напротив, элементы управления ActiveX в Windows Forms не могут использовать преимущества, которые появились в результате усовершенствования безопасности.  Для запуска элемента управления ActiveX требуется разрешение на запуск неуправляемого кода, которое устанавливается свойством <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=fullName>.  Дополнительные сведения о безопасности и разрешениях неуправляемого кода см. в разделе [Класс SecurityPermissionAttribute](frlrfSystemSecurityPermissionsSecurityPermissionAttributeClassTopic).  
  
-   **Совокупная стоимость владения** Элементы управления ActiveX, добавляемые в форму Windows Forms, развертываются полностью вместе с формой, что может существенно увеличить размер создаваемых файлов.  Помимо этого, при использовании элементов управления ActiveX в Windows Forms требуется записывать данные в реестр.  Такое поведение является более активным по отношению к компьютеру пользователя, чем поведение элементов управления Windows Forms, которые не нуждаются в этом.  
  
    > [!NOTE]
    >  Для работы с элементами управления ActiveX требуется использование оболочки взаимодействия COM.  Дополнительные сведения см. в разделе [COM\-взаимодействие в Visual Basic и Visual C\#](../Topic/COM%20Interoperability%20in%20.NET%20Framework%20Applications%20\(Visual%20Basic\).md).  
  
    > [!NOTE]
    >  Если имя члена элемента управления ActiveX соответствует имени, определенному в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], то инструмент для импорта элемента управления ActiveX добавит префикс **Ctl** к имени члена при создании производного класса <xref:System.Windows.Forms.AxHost>.  Например, если у элемента управления ActiveX имеется член под именем **Layout**, он переименовывается в **CtlLayout** в классе, производном от AxHost, поскольку событие **Layout** определено в [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## См. также  
 [Практическое руководство. Добавление элементов управления ActiveX в формы Windows Forms.](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)   
 [Code Access Security](../../../../docs/framework/misc/code-access-security.md)   
 [Сравнение элементов управления и программируемых объектов в разных языках и библиотеках](http://msdn.microsoft.com/ru-ru/021f2a1b-8247-4348-a5ad-e1d9ab23004b)   
 [Размещение элементов управления в формах Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)   
 [Элементы управления Windows Forms](../../../../docs/framework/winforms/controls/index.md)