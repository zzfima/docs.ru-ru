---
title: Практическое руководство. Использование защиты данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET Framework], data protection API
- data [.NET Framework], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET Framework], data protection API
- data protection API [.NET Framework]
- decryption
- data [.NET Framework], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: 0efd677f11189b28b8efc184c04b30a047ab942b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706036"
---
# <a name="how-to-use-data-protection"></a>Практическое руководство. Использование защиты данных
Платформа .NET Framework предоставляет доступ к API защиты данных (DPAPI), который позволяет шифровать данные, используя сведения из текущей учетной записи пользователя или с текущего компьютера.  Использование API защиты данных позволяет упростить сложную задачу явного создания и хранения криптографического ключа.  
  
 Используйте класс <xref:System.Security.Cryptography.ProtectedMemory> для шифрования массива байтов в памяти.  Эта функциональность доступна в операционных системах Microsoft Windows XP и более поздних версий.  Можно указать, что память, зашифрованная текущим процессом, может быть расшифрована только текущим процессом, всеми процессами либо из того же контекста пользователя.  Подробное описание параметров <xref:System.Security.Cryptography.ProtectedMemory> см. в разделе, посвященном перечислению <xref:System.Security.Cryptography.MemoryProtectionScope>.  
  
 Используйте класс <xref:System.Security.Cryptography.ProtectedData> для шифрования копии массива байтов. Эта функциональность доступна в операционных системах Microsoft Windows 2000 и более поздних версий.  Можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы только той же учетной записью, либо можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы любой учетной записью на компьютере.  Подробное описание параметров <xref:System.Security.Cryptography.ProtectedData> см. в разделе, посвященном перечислению <xref:System.Security.Cryptography.DataProtectionScope>.  
  
### <a name="to-encrypt-in-memory-data-using-data-protection"></a>Шифрование данных в памяти при помощи функции защиты данных  
  
1. Вызовите статический метод <xref:System.Security.Cryptography.ProtectedMemory.Protect%2A> во время передачи массива байтов для шифрования, энтропии и области защиты памяти.  
  
### <a name="to-decrypt-in-memory-data-using-data-protection"></a>Расшифровка данных в памяти при помощи функции защиты данных  
  
1. Вызовите статический метод <xref:System.Security.Cryptography.ProtectedMemory.Unprotect%2A> во время передачи массива байтов для расшифровки и области защиты памяти.  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a>Шифрование данных в файл или поток при помощи функции защиты данных  
  
1. Создайте случайную энтропию.  
  
2. Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Protect%2A> во время передачи массива байтов для шифрования, энтропии и области защиты данных.  
  
3. Запишите зашифрованные данные в файл или поток.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>Расшифровка данных из файла или потока при помощи функции защиты данных  
  
1. Считайте зашифрованные данные из файла или потока.  
  
2. Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> во время передачи массива байтов для расшифровки и области защиты данных.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показаны два вида шифрования и расшифровки.  Сначала пример кода выполняет шифрование и расшифровку массива байтов в памяти.  Далее этот пример кода шифрует копию массива байтов, сохраняет его в файл, загружает данные обратно из файла и затем расшифровывает эти данные.  В примере отображаются исходные данные, зашифрованные данные и расшифрованные данные.  
  
 [!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
 [!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Включите ссылку на `System.Security.dll`.  
  
- Включите пространство имен <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> и <xref:System.Text>.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
