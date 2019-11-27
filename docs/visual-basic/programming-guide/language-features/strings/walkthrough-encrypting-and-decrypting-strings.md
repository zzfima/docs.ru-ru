---
title: Шифрование и расшифровка строк
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 36e405c7362993471d3e6da8e319bccb854e1026
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343589"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic
В этом пошаговом руководстве показано, как использовать класс <xref:System.Security.Cryptography.DESCryptoServiceProvider> для шифрования и расшифровки строк с помощью поставщика служб шифрования (CSP) алгоритма Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>). Первым шагом является создание простого класса-оболочки, который инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде строки в кодировке Base-64. Затем эта оболочка используется для безопасного хранения личных данных пользователя в общедоступном текстовом файле.  
  
 Вы можете использовать шифрование для защиты секретов пользователя (например, пароли) и сделать учетные данные недоступными для чтения неавторизованными пользователями. Это может защитить удостоверение полномочного пользователя от кражи, что защищает ресурсы пользователя и обеспечивает неподдельность. Шифрование также может защитить данные пользователя от несанкционированного доступа неавторизованными пользователями.  
  
 Дополнительные сведения см. в разделе [Службы криптографии](../../../../standard/security/cryptographic-services.md).  
  
> [!IMPORTANT]
> Rijndael (теперь называется AES [AES]) и алгоритмы 3DES обеспечивают более высокий уровень безопасности, чем DES, так как они требуют более ресурсоемких вычислений. Дополнительные сведения см. в разделах <xref:System.Security.Cryptography.DES> и <xref:System.Security.Cryptography.Rijndael>.  
  
### <a name="to-create-the-encryption-wrapper"></a>Создание оболочки шифрования  
  
1. Создайте класс `Simple3Des` для инкапсуляции методов шифрования и расшифровки.  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. Добавьте импорт пространства имен криптографии в начало файла, содержащего класс `Simple3Des`.  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. В классе `Simple3Des` добавьте частное поле для хранения поставщика служб шифрования 3DES.  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. Добавьте закрытый метод, создающий массив байтов указанной длины из хэша указанного ключа.  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. Добавьте конструктор для инициализации поставщика служб шифрования 3DES.  
  
     Параметр `key` управляет методами `EncryptData` и `DecryptData`.  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. Добавьте открытый метод, который шифрует строку.  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. Добавьте открытый метод, который расшифровывает строку.  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     Класс-оболочку теперь можно использовать для защиты пользовательских ресурсов. В этом примере он используется для безопасного хранения личных данных пользователя в общедоступном текстовом файле.  
  
### <a name="to-test-the-encryption-wrapper"></a>Тестирование оболочки шифрования  
  
1. В отдельном классе добавьте метод, который использует метод `EncryptData` оболочки для шифрования строки и записи ее в папку пользователя "Мои документы".  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. Добавьте метод, который считывает зашифрованную строку из папки пользователя "Мои документы" и расшифровывает строку с помощью метода `DecryptData` оболочки.  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. Добавьте код пользовательского интерфейса для вызова методов `TestEncoding` и `TestDecoding`.  
  
4. Запустите приложение.  
  
     При тестировании приложения Обратите внимание, что оно не будет расшифровывать данные, если указать неправильный пароль.  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [Cryptographic Services](../../../../standard/security/cryptographic-services.md)
