---
title: "Практическое руководство. Удаление раздела реестра в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0cb98c02531bac133b9dc37a92f75d5c0418dc7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a>Практическое руководство. Удаление раздела реестра в Visual Basic
Методы <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> и <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> можно использовать для удаления разделов реестра.  
  
## <a name="procedure"></a>Процедура  
  
#### <a name="to-delete-a-registry-key"></a>Удаление раздела реестра  
  
-   Для удаления раздела реестра используйте метод `DeleteSubKey`. В этом примере удаляется раздел Software/TestApp в кусте CurrentUser. Можно изменить его в коде на подходящую строку или запросить значение для этого раздела у пользователя.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Метод `DeleteSubKey` возвратит пустую строку, если пара "раздел-значение" не существует.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Имя раздела — `Nothing` (<xref:System.ArgumentNullException>).  
  
-   У пользователя нет разрешений на удаление разделов реестра (<xref:System.Security.SecurityException>).  
  
-   Имя раздела превышает ограничение в 255 символов (<xref:System.ArgumentException>).  
  
-   Раздел реестра доступен только для чтения (<xref:System.UnauthorizedAccessException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Обращение к реестру невозможно, если не предоставлены достаточные разрешения времени выполнения (<xref:System.Security.Permissions.RegistryPermission>) или у пользователя нет надлежащих прав доступа (определенных списками управления доступом) для создания или записи параметров. Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы.  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey>  
 [Безопасность и реестр](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 [Чтение данных из реестра и запись в реестр](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
