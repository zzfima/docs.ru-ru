---
title: "Обеспечение целостности данных с помощью хэш-кодов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET Framework], hash
- data integrity
- checking hash codes
- encryption [.NET Framework], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fcede920b0e57dee0449d8ff6d7c935b177dcbcd
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="df0c8-102">Обеспечение целостности данных с помощью хэш-кодов</span><span class="sxs-lookup"><span data-stu-id="df0c8-102">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="df0c8-103">Хэш-код является численным значением фиксированной длины, которое однозначно идентифицирует данные.</span><span class="sxs-lookup"><span data-stu-id="df0c8-103">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="df0c8-104">Хэш-коды представляют большие объемы данных в виде намного меньших по объему числовых значений, поэтому они используются с цифровыми подписями.</span><span class="sxs-lookup"><span data-stu-id="df0c8-104">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="df0c8-105">Хэш-код можно подписать более эффективно, чем значение большего размера.</span><span class="sxs-lookup"><span data-stu-id="df0c8-105">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="df0c8-106">Хэш-коды также могут использоваться для проверки целостности данных, пересылаемых по незащищенным каналам.</span><span class="sxs-lookup"><span data-stu-id="df0c8-106">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="df0c8-107">Хэш-код полученных данных можно сравнить с хэш-кодом этих же данных, вычисленным перед их передачей, и на основании этого определить, подвергались ли данные изменениям.</span><span class="sxs-lookup"><span data-stu-id="df0c8-107">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
 <span data-ttu-id="df0c8-108">В этом разделе описываются способы создания и проверки хэш-кодов с помощью классов пространства имен <xref:System.Security.Cryptography?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="df0c8-108">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="df0c8-109">Создание хэша</span><span class="sxs-lookup"><span data-stu-id="df0c8-109">Generating a Hash</span></span>  
 <span data-ttu-id="df0c8-110">Управляемые классы, реализующие хэширование, можно использовать для хэширования либо байтового массива, либо управляемого объекта потока.</span><span class="sxs-lookup"><span data-stu-id="df0c8-110">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="df0c8-111">В примере ниже хэш-алгоритм SHA1 используется для создания хэш-кода строки.</span><span class="sxs-lookup"><span data-stu-id="df0c8-111">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="df0c8-112">В примере класс <xref:System.Text.UnicodeEncoding> используется для преобразования строки в массив байтов, которые хэшируются с помощью класса <xref:System.Security.Cryptography.SHA1Managed>.</span><span class="sxs-lookup"><span data-stu-id="df0c8-112">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA1Managed> class.</span></span> <span data-ttu-id="df0c8-113">После этого хэш-код выводится на консоль.</span><span class="sxs-lookup"><span data-stu-id="df0c8-113">The hash value is then displayed to the console.</span></span>  
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="df0c8-114">Этот код выводит на консоль следующую строку:</span><span class="sxs-lookup"><span data-stu-id="df0c8-114">This code will display the following string to the console:</span></span>  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="df0c8-115">Проверка хэша</span><span class="sxs-lookup"><span data-stu-id="df0c8-115">Verifying a Hash</span></span>  
 <span data-ttu-id="df0c8-116">Проверку целостности данных можно производить на основании сравнения их с хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="df0c8-116">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="df0c8-117">Обычно данные хэшируются в некоторый момент времени, а затем их хэш-код защищается каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="df0c8-117">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="df0c8-118">Позже можно снова хэшировать эти данные и результат сравнивать с защищенным хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="df0c8-118">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="df0c8-119">Если хэш-коды совпадают, значит, данные не изменялись.</span><span class="sxs-lookup"><span data-stu-id="df0c8-119">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="df0c8-120">Несовпадение хэш-кодов свидетельствует о том, что данные были повреждены.</span><span class="sxs-lookup"><span data-stu-id="df0c8-120">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="df0c8-121">Чтобы такой механизм был работоспособен, защищенный хэш должен быть зашифрован или являться недоступным для всех лиц, не имеющих достаточного доверия.</span><span class="sxs-lookup"><span data-stu-id="df0c8-121">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="df0c8-122">В примере ниже ранее полученный хэш-код строки сравнивается с ее новым хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="df0c8-122">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="df0c8-123">В этом примере реализован цикл, производящий побайтовое сравнение хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="df0c8-123">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="df0c8-124">Если хэш-коды совпадают, этот код выводит на консоль следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="df0c8-124">If the two hash values match, this code displays the following to the console:</span></span>  
  
```  
The hash codes match.  
```  
  
 <span data-ttu-id="df0c8-125">В противном случае на консоль выводится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="df0c8-125">If they do not match, the code displays the following:</span></span>  
  
```  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="df0c8-126">См. также</span><span class="sxs-lookup"><span data-stu-id="df0c8-126">See Also</span></span>  
 [<span data-ttu-id="df0c8-127">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="df0c8-127">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
