---
title: "Практическое руководство. Чтение значения из раздела реестра в Visual Basic | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- registry keys, determining if a value exists in
- My.Computer.Registry object, examples
- registry, determining if values exist
- registry keys, reading from
- registry, reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e68cde6d56d4de584861b8bcf29e072a5fc18928
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a>Практическое руководство. Чтение значения из раздела реестра в Visual Basic
Для чтения значений из реестра Windows можно использовать метод `GetValue` объекта `My.Computer.Registry`.  
  
 Если раздел (в данном случае "Software\MyApp") не существует, возникает исключение. Если `ValueName` (в данном случае "Name") не существует, возвращается `Nothing`.  
  
 Метод `GetValue` также можно использовать для определения наличия заданного значения в определенном разделе реестра.  
  
 Когда код считывает реестр из веб-приложения, текущий пользователь определяется путем проверки подлинности и олицетворения, реализованного в веб-приложении.  
  
### <a name="to-read-a-value-from-a-registry-key"></a>Чтение значения из раздела реестра  
  
-   Для чтения значения из раздела реестра используйте метод `GetValue`, указав путь и имя. В следующем примере считывается значение `Name` из раздела `HKEY_CURRENT_USER\Software\MyApp`, после чего оно отображается в окне сообщения.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 Этот пример кода также доступен в качестве фрагмента кода IntelliSense. В средстве выбора фрагмента кода он расположен в разделе **Операционная система Windows > Реестр**. Дополнительные сведения см. в статье [Фрагменты кода](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a>Определение наличия значения в разделе реестра  
  
-   Чтобы получить значение, используйте метод `GetValue`. В следующем коде проверяется наличие значения и возвращается сообщение, если значение отсутствует.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Реестр содержит разделы верхнего уровня или корневые разделы, которые используются для хранения данных. Например, корневой раздел HKEY_LOCAL_MACHINE используется для хранения параметров уровня компьютера, используемых всеми пользователями, тогда как HKEY_CURRENT_USER используется для хранения данных для отдельного пользователя.  
  
 При следующих условиях возможно возникновение исключения:  
  
-   Имя раздела переставляет собой значение `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Пользователь не имеет разрешения на чтение разделов реестра (<xref:System.Security.SecurityException>).  
  
-   Длина имени раздела превышает ограничение в 255 символов (<xref:System.ArgumentException>).  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Для выполнения этого процесса сборке требуется уровень привилегий, предоставляемых классом <xref:System.Security.Permissions.RegistryPermission>. Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий. Аналогичным образом пользователь должен иметь правильные ACL для создания и записи параметров. Например, локальное приложение, имеющее разрешение на доступ к коду, может не иметь разрешения операционной системы. Дополнительные сведения см. в разделе [Основы управления доступом для кода](https://msdn.microsoft.com/library/33tceax8).  
  
## <a name="see-also"></a>См. также  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [Чтение данных из реестра и запись в реестр](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
