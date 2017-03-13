---
title: "Практическое руководство. Чтение значения из раздела реестра в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.Registry - объект, примеры"
  - "разделы реестра, определение существования значения в"
  - "разделы реестра, чтение из"
  - "реестр, определение существования значений"
  - "реестр, чтение"
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# Практическое руководство. Чтение значения из раздела реестра в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Для чтения значений из реестра Windows можно использовать метод `GetValue` объекта `My.Computer.Registry`.  
  
 Если ключ, «software \\ MyApp» в следующем примере, создается исключение.  Если `ValueName`, «имя» в следующем примере не существует, возвращается `Nothing`.  
  
 Метод `GetValue` может также использоваться для определения того, существует ли заданное значение в определенном разделе реестра.  
  
 Если код читает реестр из веб\-приложения текущий пользователь идентифицируется проверкой подлинности и олицетворения, приведенную в веб\-приложении.  
  
### Чтение значения из раздела реестра  
  
-   Для чтения значения из раздела реестра используйте метод `GetValue`, указав путь и имя.  В этом примере считывается значение `Name` из раздела `HKEY_CURRENT_USER\Software\MyApp`, после чего оно отображается в окне сообщения.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 Данный пример доступен также в качестве фрагмента кода IntelliSense.  В окне выбора фрагмента кода он расположен в разделе **Операционная система Windows \> Реестр**.  Дополнительные сведения см. в разделе [Фрагменты кода](/visual-studio/ide/code-snippets).  
  
### Определение существования значения в разделе реестра  
  
-   Для извлечения значения используйте метод `GetValue`.  Следующие проверки кода, существует ли значение, и возвращает сообщение, если это не так.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## Отказоустойчивость  
 Реестр содержит разделы верхнего уровня, или корневые разделы, которые используются для хранения данных.  Например, корневой раздел HKEY\_LOCAL\_MACHINE используется для хранения на параметров уровне компьютера, используемых всеми пользователями, в то время как HKEY\_CURRENT\_USER используется для хранения данных для отдельного пользователя.  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Имя раздела представляет собой значение `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Пользователь не имеет разрешений на чтение разделов реестра \(<xref:System.Security.SecurityException>\).  
  
-   Длина имени раздела превышает ограничение в 255 знаков \(<xref:System.ArgumentException>\).  
  
## Безопасность платформы .NET Framework  
 Для выполнения этого процесса сборке требуется уровень привилегий, предоставляемых классом <xref:System.Security.Permissions.RegistryPermission>.  Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из\-за недостатка привилегий.  Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров.  Например, локальное приложение, имеющее разрешение управления доступом для кода, может не иметь разрешения операционной системы.  Дополнительные сведения см. в разделе [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
## См. также  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [Чтение данных из реестра и запись в реестр](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)