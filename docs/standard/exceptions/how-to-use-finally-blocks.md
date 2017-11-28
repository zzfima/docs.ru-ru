---
title: "Практическое руководство. Использование блоков Finally"
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
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b303582a62f211091b1ebee0e88cf380da8b03d9
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-use-finally-blocks"></a>Использование блоков finally

При возникновении исключения выполнение останавливается, и управление передается соответствующему обработчику исключений. Часто это означает, что ожидаемые вами строки кода пропускаются. Даже при возникновении исключения требуется определенная очистка ресурсов, например закрытие файла. Для этого можно использовать блок `finally`. Блок `finally` выполняются всегда, независимо от того, возникает ли исключение.

В следующем примере кода блок `try`/`catch` используется, чтобы перехватить <xref:System.ArgumentOutOfRangeException>. Метод `Main` создает два массива и пытается скопировать один из них в другой. Это действие создает исключение <xref:System.ArgumentOutOfRangeException>, и ошибка выводится на консоль. Блок `finally` выполняется вне зависимости от результата операции копирования.

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a>См. также  
[Исключения](index.md)   
