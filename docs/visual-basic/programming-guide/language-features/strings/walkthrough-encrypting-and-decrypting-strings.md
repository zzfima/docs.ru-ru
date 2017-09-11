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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 460b0e6e84f5be23f0c811e48daf36d3d4af3d23
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="b424d-102">Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b424d-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="b424d-103">В этом пошаговом руководстве показано, как использовать <xref:System.Security.Cryptography.DESCryptoServiceProvider>класса для шифрования и расшифровки строк с помощью служб шифрования (CSP) версии Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) алгоритма.</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="b424d-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="b424d-104">Первым шагом является создание простой класс обертки, инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде строки в кодировке base-64.</span><span class="sxs-lookup"><span data-stu-id="b424d-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="b424d-105">Затем эту оболочку используется для безопасного хранения частных данных пользователя в общедоступном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="b424d-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="b424d-106">Можно использовать шифрование для защиты секретов пользователя (например, пароли), а также учетные данные не удается прочесть неавторизованные пользователи.</span><span class="sxs-lookup"><span data-stu-id="b424d-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="b424d-107">Это позволяет защитить от кражи, удостоверения авторизованного пользователя, который защищает ресурсы пользователя и гарантирует неподдельность.</span><span class="sxs-lookup"><span data-stu-id="b424d-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="b424d-108">Шифрование также может защитить данные пользователя от доступа неавторизованных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b424d-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="b424d-109">Дополнительные сведения см. в разделе [службы криптографии](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).</span><span class="sxs-lookup"><span data-stu-id="b424d-109">For more information, see [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b424d-110">Rijndael (также известный как расширенный стандарт шифрования [AES]) и алгоритма Triple Data Encryption Standard (3DES) обеспечивают большую безопасность, чем DES, из-за большего большим объемом вычислений.</span><span class="sxs-lookup"><span data-stu-id="b424d-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="b424d-111">Дополнительные сведения см. в разделе <xref:System.Security.Cryptography.DES>и <xref:System.Security.Cryptography.Rijndael>.</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="b424d-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="b424d-112">Создание оболочки шифрования</span><span class="sxs-lookup"><span data-stu-id="b424d-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="b424d-113">Создайте `Simple3Des` класс для инкапсуляции методов шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="b424d-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     <span data-ttu-id="b424d-114">[!code-vb[VbVbalrStrings&#38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-114">[!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span></span>  
  
2.  <span data-ttu-id="b424d-115">Добавьте в начало файла, содержащего импорт имен криптографии `Simple3Des` класса.</span><span class="sxs-lookup"><span data-stu-id="b424d-115">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     <span data-ttu-id="b424d-116">[!code-vb[VbVbalrStrings&#77;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-116">[!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span></span>  
  
3.  <span data-ttu-id="b424d-117">В `Simple3Des` добавьте закрытое поле для хранения поставщика служб шифрования 3DES.</span><span class="sxs-lookup"><span data-stu-id="b424d-117">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="b424d-118">[!code-vb[VbVbalrStrings&#39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-118">[!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span></span>  
  
4.  <span data-ttu-id="b424d-119">Добавьте закрытый метод, который создает массив байтов указанной длины из хэша указанного ключа.</span><span class="sxs-lookup"><span data-stu-id="b424d-119">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     <span data-ttu-id="b424d-120">[!code-vb[VbVbalrStrings&#41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-120">[!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span></span>  
  
5.  <span data-ttu-id="b424d-121">Добавьте конструктор для инициализации поставщика служб шифрования 3DES.</span><span class="sxs-lookup"><span data-stu-id="b424d-121">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="b424d-122">`key` Элементов управления параметрами `EncryptData` и `DecryptData` методы.</span><span class="sxs-lookup"><span data-stu-id="b424d-122">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     <span data-ttu-id="b424d-123">[!code-vb[VbVbalrStrings&#40;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-123">[!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span></span>  
  
6.  <span data-ttu-id="b424d-124">Добавьте открытый метод, который шифрует строку.</span><span class="sxs-lookup"><span data-stu-id="b424d-124">Add a public method that encrypts a string.</span></span>  
  
     <span data-ttu-id="b424d-125">[!code-vb[VbVbalrStrings&#42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-125">[!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span></span>  
  
7.  <span data-ttu-id="b424d-126">Добавьте открытый метод, который расшифровывает строку.</span><span class="sxs-lookup"><span data-stu-id="b424d-126">Add a public method that decrypts a string.</span></span>  
  
     <span data-ttu-id="b424d-127">[!code-vb[VbVbalrStrings&#43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-127">[!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span></span>  
  
     <span data-ttu-id="b424d-128">Класс-оболочку теперь могут использоваться для защиты ресурсов пользователей.</span><span class="sxs-lookup"><span data-stu-id="b424d-128">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="b424d-129">В этом примере используется для безопасного хранения частных данных пользователя в общедоступном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="b424d-129">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="b424d-130">Чтобы проверить оболочки шифрования</span><span class="sxs-lookup"><span data-stu-id="b424d-130">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="b424d-131">В отдельном классе добавьте метод, который использует оболочку `EncryptData` метод, чтобы зашифровать строку и записать его для пользователя в папку «Мои документы».</span><span class="sxs-lookup"><span data-stu-id="b424d-131">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     <span data-ttu-id="b424d-132">[!code-vb[VbVbalrStrings&#78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-132">[!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span></span>  
  
2.  <span data-ttu-id="b424d-133">Добавьте метод, который считывает зашифрованную строку от пользователя в папку «Мои документы» и расшифровывает строку в оболочку `DecryptData` метод.</span><span class="sxs-lookup"><span data-stu-id="b424d-133">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     <span data-ttu-id="b424d-134">[!code-vb[VbVbalrStrings&#79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="b424d-134">[!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span></span>  
  
3.  <span data-ttu-id="b424d-135">Добавьте код пользовательского интерфейса для вызова `TestEncoding` и `TestDecoding` методы.</span><span class="sxs-lookup"><span data-stu-id="b424d-135">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="b424d-136">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="b424d-136">Run the application.</span></span>  
  
     <span data-ttu-id="b424d-137">При тестировании приложения, обратите внимание, что оно не будет расшифровывать данные при вводе неправильного пароля.</span><span class="sxs-lookup"><span data-stu-id="b424d-137">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b424d-138">См. также</span><span class="sxs-lookup"><span data-stu-id="b424d-138">See Also</span></span>  
 <span data-ttu-id="b424d-139"><xref:System.Security.Cryptography></xref:System.Security.Cryptography></span><span class="sxs-lookup"><span data-stu-id="b424d-139"><xref:System.Security.Cryptography></span></span>   
 <span data-ttu-id="b424d-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="b424d-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></span></span>   
 <span data-ttu-id="b424d-141"><xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="b424d-141"><xref:System.Security.Cryptography.DES></span></span>   
 <span data-ttu-id="b424d-142"><xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES></span><span class="sxs-lookup"><span data-stu-id="b424d-142"><xref:System.Security.Cryptography.TripleDES></span></span>   
 <span data-ttu-id="b424d-143"><xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael></span><span class="sxs-lookup"><span data-stu-id="b424d-143"><xref:System.Security.Cryptography.Rijndael></span></span>   
<span data-ttu-id="b424d-144"> [Службы криптографии](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span><span class="sxs-lookup"><span data-stu-id="b424d-144"> [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span></span>
