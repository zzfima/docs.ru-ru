---
title: "Шифрование и расшифровка строк в Visual Basic | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- encryption, strings
- strings [Visual Basic], encrypting
- decryption, strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ae3d599f7173162c07fbaeda60435615f101b10d
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic
В этом пошаговом руководстве показано, как использовать <xref:System.Security.Cryptography.DESCryptoServiceProvider>класса для шифрования и расшифровки строк с помощью служб шифрования (CSP) версии Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) алгоритма.</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider> Первым шагом является создание простой класс обертки, инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде строки в кодировке base-64. Затем эту оболочку используется для безопасного хранения частных данных пользователя в общедоступном текстовом файле.  
  
 Можно использовать шифрование для защиты секретов пользователя (например, пароли), а также учетные данные не удается прочесть неавторизованные пользователи. Это позволяет защитить от кражи, удостоверения авторизованного пользователя, который защищает ресурсы пользователя и гарантирует неподдельность. Шифрование также может защитить данные пользователя от доступа неавторизованных пользователей.  
  
 Дополнительные сведения см. в разделе [службы криптографии](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).  
  
> [!IMPORTANT]
>  Rijndael (также известный как расширенный стандарт шифрования [AES]) и алгоритма Triple Data Encryption Standard (3DES) обеспечивают большую безопасность, чем DES, из-за большего большим объемом вычислений. Дополнительные сведения см. в разделе <xref:System.Security.Cryptography.DES>и <xref:System.Security.Cryptography.Rijndael>.</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES>  
  
### <a name="to-create-the-encryption-wrapper"></a>Создание оболочки шифрования  
  
1.  Создайте `Simple3Des` класс для инкапсуляции методов шифрования и расшифровки.  
  
     [!code-vb[VbVbalrStrings&#38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Добавьте в начало файла, содержащего импорт имен криптографии `Simple3Des` класса.  
  
     [!code-vb[VbVbalrStrings&#77;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  В `Simple3Des` добавьте закрытое поле для хранения поставщика служб шифрования 3DES.  
  
     [!code-vb[VbVbalrStrings&#39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Добавьте закрытый метод, который создает массив байтов указанной длины из хэша указанного ключа.  
  
     [!code-vb[VbVbalrStrings&#41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Добавьте конструктор для инициализации поставщика служб шифрования 3DES.  
  
     `key` Элементов управления параметрами `EncryptData` и `DecryptData` методы.  
  
     [!code-vb[VbVbalrStrings&#40;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Добавьте открытый метод, который шифрует строку.  
  
     [!code-vb[VbVbalrStrings&#42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Добавьте открытый метод, который расшифровывает строку.  
  
     [!code-vb[VbVbalrStrings&#43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Класс-оболочку теперь могут использоваться для защиты ресурсов пользователей. В этом примере используется для безопасного хранения частных данных пользователя в общедоступном текстовом файле.  
  
### <a name="to-test-the-encryption-wrapper"></a>Чтобы проверить оболочки шифрования  
  
1.  В отдельном классе добавьте метод, который использует оболочку `EncryptData` метод, чтобы зашифровать строку и записать его для пользователя в папку «Мои документы».  
  
     [!code-vb[VbVbalrStrings&#78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Добавьте метод, который считывает зашифрованную строку от пользователя в папку «Мои документы» и расшифровывает строку в оболочку `DecryptData` метод.  
  
     [!code-vb[VbVbalrStrings&#79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Добавьте код пользовательского интерфейса для вызова `TestEncoding` и `TestDecoding` методы.  
  
4.  Запустите приложение.  
  
     При тестировании приложения, обратите внимание, что оно не будет расшифровывать данные при вводе неправильного пароля.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Security.Cryptography></xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael>   
 [Службы криптографии](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)
