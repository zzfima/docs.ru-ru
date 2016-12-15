---
title: "Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "расшифровка, строки"
  - "шифрование, строки"
  - "строки [Visual Basic], расшифровка"
  - "строки [Visual Basic], шифрование"
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

В этом примере демонстрируется использование <xref:System.Security.Cryptography.DESCryptoServiceProvider> класса для шифрования и расшифровки строк с помощью версии стандартного алгоритма шифрования данных Triple \(<xref:System.Security.Cryptography.TripleDES>\) поставщика служб шифрования \(CSP\).  Первым шагом является создание простого класса\-оболочки, который инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде зашифрованной строки base\-64.  Затем оболочка используется для безопасного хранения собственных данных пользователя в общедоступном текстовом файле.  
  
 Можно использовать шифрование для защиты секретов пользователя \(например паролей\) и создания учетных данных, которые недоступны для чтения неавторизованным пользователям.  Это позволяет защитить от кражи удостоверения авторизованного пользователя, что защищает ресурсы пользователя и гарантирует неподдельность.  Шифрование также может защитить данные пользователя от доступа неавторизованных пользователей.  
  
 Дополнительные сведения см. в разделе [Службы криптографии](../Topic/Cryptographic%20Services.md).  
  
> [!IMPORTANT]
>  Rijndael \(также известный как расширенный стандарт шифрования \[AES\]\) и стандарт шифрования данных Triple \(3DES\) обеспечивают более высокую степень безопасности, чем DES, из\-за большего объёма вычислений.  Дополнительные сведения см. в разделах <xref:System.Security.Cryptography.DES> и <xref:System.Security.Cryptography.Rijndael>.  
  
### Создание оболочки шифрования  
  
1.  Создайте класс `Simple3Des` для инкапсуляции методов шифрования и расшифровки.  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  Добавьте импорт пространства имен шифрования к началу файла, который содержит класс `Simple3Des`.  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  В классе `Simple3Des` добавьте закрытое поле для хранения поставщика служб шифрования 3DES.  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  Добавьте закрытый метод, который создает массив байтов указанной длины из хэша указанного ключа.  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  Добавьте конструктор для инициализации поставщика служб шифрования 3DES.  
  
     Параметр `key` управляет методами `EncryptData` и `DecryptData`.  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  Добавьте открытый метод, который шифрует строку.  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  Добавьте открытый метод, который расшифровывает строку.  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     Класс\-оболочку теперь можно использовать для защиты ресурсов пользователей.  В данном примере он используется для безопасного хранения частных данных пользователя в общедоступном текстовом файле.  
  
### Проверка оболочки шифрования  
  
1.  В отдельном классе добавьте метод, использующий метод `EncryptData` оболочки, чтобы зашифровать строку и записать ее в папку "Мои документы" пользователя.  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  Добавьте метод, который считывает зашифрованную строку из папки "Мои документы" пользователя и расшифровывает строку с помощью метода оболочки `DecryptData`.  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  Добавьте код пользовательского интерфейса для вызова методов `TestEncoding` и `TestDecoding`.  
  
4.  Запустите приложение.  
  
     При тестировании приложения, обратите внимание, что оно не будет расшифровывать данные при вводе неправильного пароля.  
  
## См. также  
 <xref:System.Security.Cryptography>   
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>   
 <xref:System.Security.Cryptography.DES>   
 <xref:System.Security.Cryptography.TripleDES>   
 <xref:System.Security.Cryptography.Rijndael>   
 [Службы криптографии](../Topic/Cryptographic%20Services.md)