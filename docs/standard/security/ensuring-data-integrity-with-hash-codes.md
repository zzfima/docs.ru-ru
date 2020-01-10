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
# <a name="ensuring-data-integrity-with-hash-codes"></a>Обеспечение целостности данных с помощью хэш-кодов
Хэш-код является численным значением фиксированной длины, которое однозначно идентифицирует данные. Хэш-коды представляют большие объемы данных в виде намного меньших по объему числовых значений, поэтому они используются с цифровыми подписями. Хэш-код можно подписать более эффективно, чем значение большего размера. Хэш-коды также могут использоваться для проверки целостности данных, пересылаемых по незащищенным каналам. Хэш-код полученных данных можно сравнить с хэш-кодом этих же данных, вычисленным перед их передачей, и на основании этого определить, подвергались ли данные изменениям.  
  
 В этом разделе описываются способы создания и проверки хэш-кодов с помощью классов пространства имен <xref:System.Security.Cryptography?displayProperty=nameWithType>.  
  
## <a name="generating-a-hash"></a>Создание хэша  
 Управляемые классы, реализующие хэширование, можно использовать для хэширования либо байтового массива, либо управляемого объекта потока. В примере ниже хэш-алгоритм SHA1 используется для создания хэш-кода строки. В примере класс <xref:System.Text.UnicodeEncoding> используется для преобразования строки в массив байтов, которые хэшируются с помощью класса <xref:System.Security.Cryptography.SHA1Managed>. После этого хэш-код выводится на консоль.  

 Из-за проблем с алгоритмом SHA1 Корпорация Майкрософт рекомендует использовать SHA256 или более высокий уровень.
  
 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 Этот код выводит на консоль следующую строку:  
  
 `59 4 248 102 77 97 142 201 210 12 224 93 25 41 100 197 213 134 130 135`  
  
## <a name="verifying-a-hash"></a>Проверка хэша  
 Проверку целостности данных можно производить на основании сравнения их с хэш-кодом. Обычно данные хэшируются в некоторый момент времени, а затем их хэш-код защищается каким-либо образом. Позже можно снова хэшировать эти данные и результат сравнивать с защищенным хэш-кодом. Если хэш-коды совпадают, значит, данные не изменялись. Несовпадение хэш-кодов свидетельствует о том, что данные были повреждены. Чтобы такой механизм был работоспособен, защищенный хэш должен быть зашифрован или являться недоступным для всех лиц, не имеющих достаточного доверия.  
  
 В примере ниже ранее полученный хэш-код строки сравнивается с ее новым хэш-кодом. В этом примере реализован цикл, производящий побайтовое сравнение хэш-кодов.  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 Если хэш-коды совпадают, этот код выводит на консоль следующее сообщение:  
  
```console  
The hash codes match.  
```  
  
 В противном случае на консоль выводится следующее сообщение:  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a>См. также:

- [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)
