---
title: "Практическое руководство. Создание раздела в реестре (Visual C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 96d34df3314494fc96ad8b55d7462b67dcc7bd72
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a>Практическое руководство. Создание раздела в реестре (Visual C#)
Код в этом примере добавляет в раздел Names реестра текущего пользователя пару значений — Name и Isabella.  
  
## <a name="example"></a>Пример  
  
```  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Скопируйте код и вставьте его в метод `Main` консольного приложения.  
  
-   Замените параметр `Names` на имя ключа, который находится прямо в узле HKEY_CURRENT_USER реестра.  
  
-   Замените параметр `Name` на имя значения, которое находится прямо в узле Names.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Проверьте структуру реестра и найдите подходящее место для ключа. Для этого можно, например, открыть ключ программного обеспечения текущего пользователя и создать ключ с названием вашей компании. Затем добавьте в ключ компании значения реестра.  
  
 При следующих условиях может возникнуть исключение:  
  
-   Пустое имя ключа.  
  
-   У пользователя нет разрешения на создание разделов реестра.  
  
-   Имя ключа превышает ограничение в 255 символов.  
  
-   Раздел является закрытым.  
  
-   Раздел реестра доступен только для чтения.  
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Безопаснее записывать данные в папку пользователя (`Microsoft.Win32.Registry.CurrentUser`), чем на локальный компьютер (`Microsoft.Win32.Registry.LocalMachine`).  
  
 Создавая значение реестра, необходимо решить, что делать, если это значение уже существует. Другой процесс (возможно, вредоносный) мог уже создать это значение и получить к нему доступ. Данные, добавленные в значение реестра, становятся доступными для другого процесса. Чтобы этого избежать, используйте `Overload:Microsoft.Win32.RegistryKey.GetValue` метод. Он возвращает значение NULL, если раздел еще не существует.  
  
 Небезопасно хранить секретные данные (например, пароли) в реестре как обычный текст, даже если раздел реестра защищен с помощью списков управления доступом (ACL).  
  
## <a name="see-also"></a>См. также  
 <xref:System.IO?displayProperty=fullName>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)   
 [Чтение, запись и удаление данных реестра с помощью C#](http://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)

