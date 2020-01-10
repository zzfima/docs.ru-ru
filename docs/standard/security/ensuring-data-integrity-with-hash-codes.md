---
title: Обеспечение целостности данных с помощью хэш-кодов
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: 98bdce59ccbbb3b1d00ea5521169214c2bd7a10b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706205"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="80637-102">Обеспечение целостности данных с помощью хэш-кодов</span><span class="sxs-lookup"><span data-stu-id="80637-102">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="80637-103">Хэш-код является численным значением фиксированной длины, которое однозначно идентифицирует данные.</span><span class="sxs-lookup"><span data-stu-id="80637-103">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="80637-104">Хэш-коды представляют большие объемы данных в виде намного меньших по объему числовых значений, поэтому они используются с цифровыми подписями.</span><span class="sxs-lookup"><span data-stu-id="80637-104">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="80637-105">Хэш-код можно подписать более эффективно, чем значение большего размера.</span><span class="sxs-lookup"><span data-stu-id="80637-105">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="80637-106">Хэш-коды также могут использоваться для проверки целостности данных, пересылаемых по незащищенным каналам.</span><span class="sxs-lookup"><span data-stu-id="80637-106">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="80637-107">Хэш-код полученных данных можно сравнить с хэш-кодом этих же данных, вычисленным перед их передачей, и на основании этого определить, подвергались ли данные изменениям.</span><span class="sxs-lookup"><span data-stu-id="80637-107">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
 <span data-ttu-id="80637-108">В этом разделе описываются способы создания и проверки хэш-кодов с помощью классов пространства имен <xref:System.Security.Cryptography?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80637-108">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="80637-109">Создание хэша</span><span class="sxs-lookup"><span data-stu-id="80637-109">Generating a Hash</span></span>  
 <span data-ttu-id="80637-110">Управляемые классы, реализующие хэширование, можно использовать для хэширования либо байтового массива, либо управляемого объекта потока.</span><span class="sxs-lookup"><span data-stu-id="80637-110">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="80637-111">В примере ниже хэш-алгоритм SHA1 используется для создания хэш-кода строки.</span><span class="sxs-lookup"><span data-stu-id="80637-111">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="80637-112">В примере класс <xref:System.Text.UnicodeEncoding> используется для преобразования строки в массив байтов, которые хэшируются с помощью класса <xref:System.Security.Cryptography.SHA1Managed>.</span><span class="sxs-lookup"><span data-stu-id="80637-112">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA1Managed> class.</span></span> <span data-ttu-id="80637-113">После этого хэш-код выводится на консоль.</span><span class="sxs-lookup"><span data-stu-id="80637-113">The hash value is then displayed to the console.</span></span>  

 <span data-ttu-id="80637-114">Из-за проблем с алгоритмом SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="80637-114">Due to collision problems with SHA1, Microsoft recommends SHA256 or better.</span></span>
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="80637-115">Этот код выводит на консоль следующую строку:</span><span class="sxs-lookup"><span data-stu-id="80637-115">This code will display the following string to the console:</span></span>  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="80637-116">Проверка хэша</span><span class="sxs-lookup"><span data-stu-id="80637-116">Verifying a Hash</span></span>  
 <span data-ttu-id="80637-117">Проверку целостности данных можно производить на основании сравнения их с хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="80637-117">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="80637-118">Обычно данные хэшируются в некоторый момент времени, а затем их хэш-код защищается каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="80637-118">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="80637-119">Позже можно снова хэшировать эти данные и результат сравнивать с защищенным хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="80637-119">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="80637-120">Если хэш-коды совпадают, значит, данные не изменялись.</span><span class="sxs-lookup"><span data-stu-id="80637-120">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="80637-121">Несовпадение хэш-кодов свидетельствует о том, что данные были повреждены.</span><span class="sxs-lookup"><span data-stu-id="80637-121">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="80637-122">Чтобы такой механизм был работоспособен, защищенный хэш должен быть зашифрован или являться недоступным для всех лиц, не имеющих достаточного доверия.</span><span class="sxs-lookup"><span data-stu-id="80637-122">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="80637-123">В примере ниже ранее полученный хэш-код строки сравнивается с ее новым хэш-кодом.</span><span class="sxs-lookup"><span data-stu-id="80637-123">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="80637-124">В этом примере реализован цикл, производящий побайтовое сравнение хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="80637-124">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="80637-125">Если хэш-коды совпадают, этот код выводит на консоль следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="80637-125">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="80637-126">В противном случае на консоль выводится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="80637-126">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="80637-127">См. также:</span><span class="sxs-lookup"><span data-stu-id="80637-127">See also</span></span>

- [<span data-ttu-id="80637-128">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="80637-128">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
