---
title: Шифрование и расшифровка строк в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: ee3bcd1358536e6fd9bed5c4fec7845fdf441d86
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723489"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic
В этом пошаговом руководстве показано, как использовать <xref:System.Security.Cryptography.DESCryptoServiceProvider> класса для шифрования и расшифровки строк с помощью служб шифрования (CSP) версии Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) алгоритма. Первым шагом является создание простой оболочкой класс, который инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде строки в кодировке base-64. Затем эту оболочку используется для безопасного хранения личных данных пользователей в общедоступном текстовом файле.  
  
 Можно использовать шифрование для защиты секретов пользователя (например, пароли) и создания учетных данных может быть прочитан неавторизованные пользователи. Это позволяет защитить от кражи, удостоверения авторизованного пользователя, который защищает ресурсы пользователя и предоставляет неподдельность. Шифрование также можно защитить пользовательские данные от несанкционированного доступа.  
  
 Дополнительные сведения см. в разделе [Службы криптографии](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Rijndael (теперь называется Advanced Encryption Standard [AES]) и алгоритмов Triple Data Encryption Standard (3DES) обеспечивают большую безопасность, чем DES, так как они больше с большим объемом вычислений. Дополнительные сведения см. в разделах <xref:System.Security.Cryptography.DES> и <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Для создания оболочки шифрования  
  
1.  Создание `Simple3Des` класс для инкапсуляции методы шифрования и расшифровки.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Добавьте в начало файла, содержащего функцию импорта имен криптографии `Simple3Des` класса.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  В `Simple3Des` добавьте закрытое поле для хранения поставщика служб шифрования 3DES.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Добавьте закрытый метод, который создает массив байтов указанной длины из хэша указанного ключа.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Добавьте конструктор для инициализации поставщика служб шифрования 3DES.  
  
     `key` Элементов управления параметрами `EncryptData` и `DecryptData` методы.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Добавьте открытый метод, который шифрует строку.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Добавьте открытый метод, который расшифровывает строку.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Класс-оболочку, теперь могут использоваться для защиты ресурсов пользователей. В этом примере он используется для безопасного хранения личных данных пользователей в общедоступном текстовом файле.  
  
### <a name="to-test-the-encryption-wrapper"></a>Для тестирования оболочки шифрования  
  
1.  В отдельном классе, добавьте метод, который использует оболочку `EncryptData` метод, чтобы зашифровать строку и записать ее пользователю и папка «Мои документы».  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Добавьте метод, который считывает зашифрованную строку из пользователя, и папка «Мои документы» и расшифровывает строку с помощью оболочки `DecryptData` метод.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Добавьте код пользовательского интерфейса для вызова `TestEncoding` и `TestDecoding` методы.  
  
4.  Запустите приложение.  
  
     При тестировании приложения, обратите внимание на то, что он будет не расшифровывать данные, если указать неправильный пароль.  
  
## <a name="see-also"></a>См. также
- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
