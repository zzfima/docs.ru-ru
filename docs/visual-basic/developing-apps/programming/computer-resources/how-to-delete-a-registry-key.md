---
title: "Практическое руководство. Удаление раздела реестра в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.DeleteSetting
dev_langs:
- VB
helpviewer_keywords:
- GetSetting function
- registry, deleting values
- GetAllSettings function
- registry keys, deleting
- registry, deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a50ee5a0853e6209c3bf5d5224d536f4cc6bbe11
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

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
