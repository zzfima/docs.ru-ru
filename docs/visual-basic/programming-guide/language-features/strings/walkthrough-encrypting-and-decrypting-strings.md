---
title: Шифрование и расшифровка строк в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 96e56ab315a739fef9d5499b076a077f5294f39e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651227"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic
В этом пошаговом руководстве показано, как использовать <xref:System.Security.Cryptography.DESCryptoServiceProvider> класса для шифрования и дешифрования строк с помощью служб шифрования (CSP) версии тройного шифрования данных (<xref:System.Security.Cryptography.TripleDES>) алгоритма. Первым шагом является создание простой программы-оболочки класс, который инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде строки в кодировке base-64. Затем эту оболочку используется для безопасного хранения личных данных пользователя в общедоступном текстовом файле.  
  
 Можно использовать шифрование для защиты секретов пользователя (например, пароли) и создания учетных данных может быть прочитан неавторизованные пользователи. Это позволяет защитить от кражи, удостоверения авторизованного пользователя, который защищает ресурсы пользователя и гарантирует неподдельность. Шифрование можно также защитить данные пользователя из от несанкционированного доступа.  
  
 Дополнительные сведения см. в разделе [Службы криптографии](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
>  Rijndael (также известный как расширенный стандарт шифрования [AES]) и алгоритмы тройного шифрования данных (3DES) обеспечивают большую безопасность, чем DES, из-за большего большим объемом вычислений. Дополнительные сведения см. в разделах <xref:System.Security.Cryptography.DES> и <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Для создания оболочки шифрования  
  
1.  Создайте `Simple3Des` класс для инкапсуляции методов шифрования и расшифровки.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Подключите пространство имен криптографии в начало файла, содержащего `Simple3Des` класса.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  В `Simple3Des` класса, добавьте закрытое поле для хранения поставщика служб шифрования 3DES.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Добавьте закрытый метод, который создает массив байтов указанной длины из хэша с указанным ключом.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Добавьте конструктор для инициализации поставщика служб шифрования 3DES.  
  
     `key` Управляет `EncryptData` и `DecryptData` методы.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Добавьте открытый метод, который шифрует строку.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Добавьте открытый метод, который расшифровывает строку.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Класс-оболочку теперь может использоваться для защиты ресурсов пользователей. В этом примере он используется для безопасного хранения личных данных пользователя в общедоступном текстовом файле.  
  
### <a name="to-test-the-encryption-wrapper"></a>Чтобы проверить оболочки шифрования  
  
1.  В отдельном классе добавьте метод, который использует оболочку `EncryptData` метод, чтобы зашифровать строку и записать ее для пользователя этого папка «Мои документы».  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Добавить метод, который считывает зашифрованную строку из пользователя папка «Мои документы» и расшифровывает строку в оболочку `DecryptData` метод.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Добавьте код пользовательского интерфейса для вызова `TestEncoding` и `TestDecoding` методы.  
  
4.  Запустите приложение.  
  
     При тестировании приложения, обратите внимание, что оно не будет расшифровывать данные, если указать неправильный пароль.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [Службы криптографии](../../../../standard/security/cryptographic-services.md)
