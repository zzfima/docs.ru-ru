---
title: Практическое руководство. Создание раздела в реестре (Visual C#)
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: a3a6af8eb493ce17ac73769decd1f60b903ae165
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49337614"
---
# <a name="how-to-create-a-key-in-the-registry-visual-c"></a>Практическое руководство. Создание раздела в реестре (Visual C#)
Код в этом примере добавляет в раздел Names реестра текущего пользователя пару значений — Name и Isabella.  
  
## <a name="example"></a>Пример  
  
```csharp  
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

- <xref:System.IO?displayProperty=nameWithType>  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Файловая система и реестр (руководство по программированию на C#)](../../../csharp/programming-guide/file-system/index.md)  
- [Чтение, запись и удаление данных реестра с помощью C#](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
