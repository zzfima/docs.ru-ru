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
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="3c5bf-102">Пошаговое руководство. Шифрование и расшифровка строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c5bf-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="3c5bf-103">В этом пошаговом руководстве показано, как использовать <xref:System.Security.Cryptography.DESCryptoServiceProvider> класса для шифрования и дешифрования строк с помощью служб шифрования (CSP) версии тройного шифрования данных (<xref:System.Security.Cryptography.TripleDES>) алгоритма.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="3c5bf-104">Первым шагом является создание простой программы-оболочки класс, который инкапсулирует алгоритм 3DES и сохраняет зашифрованные данные в виде строки в кодировке base-64.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="3c5bf-105">Затем эту оболочку используется для безопасного хранения личных данных пользователя в общедоступном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="3c5bf-106">Можно использовать шифрование для защиты секретов пользователя (например, пароли) и создания учетных данных может быть прочитан неавторизованные пользователи.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="3c5bf-107">Это позволяет защитить от кражи, удостоверения авторизованного пользователя, который защищает ресурсы пользователя и гарантирует неподдельность.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="3c5bf-108">Шифрование можно также защитить данные пользователя из от несанкционированного доступа.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="3c5bf-109">Дополнительные сведения см. в разделе [Службы криптографии](../../../../standard/security/cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="3c5bf-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c5bf-110">Rijndael (также известный как расширенный стандарт шифрования [AES]) и алгоритмы тройного шифрования данных (3DES) обеспечивают большую безопасность, чем DES, из-за большего большим объемом вычислений.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="3c5bf-111">Дополнительные сведения см. в разделах <xref:System.Security.Cryptography.DES> и <xref:System.Security.Cryptography.Rijndael>.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="3c5bf-112">Для создания оболочки шифрования</span><span class="sxs-lookup"><span data-stu-id="3c5bf-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="3c5bf-113">Создайте `Simple3Des` класс для инкапсуляции методов шифрования и расшифровки.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  <span data-ttu-id="3c5bf-114">Подключите пространство имен криптографии в начало файла, содержащего `Simple3Des` класса.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  <span data-ttu-id="3c5bf-115">В `Simple3Des` класса, добавьте закрытое поле для хранения поставщика служб шифрования 3DES.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  <span data-ttu-id="3c5bf-116">Добавьте закрытый метод, который создает массив байтов указанной длины из хэша с указанным ключом.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  <span data-ttu-id="3c5bf-117">Добавьте конструктор для инициализации поставщика служб шифрования 3DES.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="3c5bf-118">`key` Управляет `EncryptData` и `DecryptData` методы.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  <span data-ttu-id="3c5bf-119">Добавьте открытый метод, который шифрует строку.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  <span data-ttu-id="3c5bf-120">Добавьте открытый метод, который расшифровывает строку.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     <span data-ttu-id="3c5bf-121">Класс-оболочку теперь может использоваться для защиты ресурсов пользователей.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="3c5bf-122">В этом примере он используется для безопасного хранения личных данных пользователя в общедоступном текстовом файле.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="3c5bf-123">Чтобы проверить оболочки шифрования</span><span class="sxs-lookup"><span data-stu-id="3c5bf-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="3c5bf-124">В отдельном классе добавьте метод, который использует оболочку `EncryptData` метод, чтобы зашифровать строку и записать ее для пользователя этого папка «Мои документы».</span><span class="sxs-lookup"><span data-stu-id="3c5bf-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  <span data-ttu-id="3c5bf-125">Добавить метод, который считывает зашифрованную строку из пользователя папка «Мои документы» и расшифровывает строку в оболочку `DecryptData` метод.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  <span data-ttu-id="3c5bf-126">Добавьте код пользовательского интерфейса для вызова `TestEncoding` и `TestDecoding` методы.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="3c5bf-127">Запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-127">Run the application.</span></span>  
  
     <span data-ttu-id="3c5bf-128">При тестировании приложения, обратите внимание, что оно не будет расшифровывать данные, если указать неправильный пароль.</span><span class="sxs-lookup"><span data-stu-id="3c5bf-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5bf-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3c5bf-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [<span data-ttu-id="3c5bf-130">Службы криптографии</span><span class="sxs-lookup"><span data-stu-id="3c5bf-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
