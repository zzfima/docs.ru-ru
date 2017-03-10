---
title: "Практическое руководство. Удаление раздела реестра в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.DeleteSetting"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "примеры [Visual Basic], реестр"
  - "GetAllSettings - функция"
  - "GetSetting - функция"
  - "разделы реестра, удаление"
  - "реестр, удаление ключей"
  - "реестр, удаление значений"
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 28
---
# Практическое руководство. Удаление раздела реестра в Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Для удаления разделов реестра можно использовать методы <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> и <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29>.  
  
## Процедура  
  
#### Удаление раздела реестра  
  
-   Для удаления раздела реестра используйте метод `DeleteSubKey`.  В этом примере удаляется раздел SOFTWARE\/TestApp в кусте CurrentUser.  Можно изменить его в коде на подходящую строку или запросить значение для этого раздела у пользователя.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-delete-a-registry_1.vb)]  
  
## Отказоустойчивость  
 Если пара раздел\/значение не существует, метод `DeleteSubKey` возвратит пустую строку.  
  
 При следующих условиях возможно возникновение исключения.  
  
-   Имя раздела представляет собой значение `Nothing` \(<xref:System.ArgumentNullException>\).  
  
-   Пользователь не имеет разрешений на удаление разделов реестра \(<xref:System.Security.SecurityException>\).  
  
-   Длина имени раздела превышает ограничение в 255 знаков \(<xref:System.ArgumentException>\).  
  
-   Раздел реестра доступен только для чтения \(<xref:System.UnauthorizedAccessException>\).  
  
## Безопасность платформы .NET Framework  
 Обращение к реестру невозможно, если не предоставлены достаточные разрешения времени выполнения \(<xref:System.Security.Permissions.RegistryPermission>\) или у пользователя нет надлежащих прав доступа \(определенных списками управления доступом\) для создания или записи параметров.  Например, локальное приложение, имеющее разрешение управления доступом для кода, может не иметь разрешения операционной системы.  
  
## См. также  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey>   
 [Безопасность и реестр](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)   
 [Чтение данных из реестра и запись в реестр](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)