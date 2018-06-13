---
title: Практическое руководство. Явное создание исключения
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4eeb70c10d71a7c96136039342bcdcc7bc8ece20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570353"
---
# <a name="how-to-explicitly-throw-exceptions"></a>Явное создание исключений

Исключение можно вызвать явным образом с помощью оператора `throw`. Перехваченное исключение можно вызвать повторно с помощью оператора `throw`. При написании кода рекомендуется добавлять сведения в исключение, которое выдается повторно, чтобы предоставить дополнительную информацию при отладке.

В следующем примере кода блок `try`/`catch` используется, чтобы перехватить возможное <xref:System.IO.FileNotFoundException>. После блока `try` находится блок `catch`, который перехватывает <xref:System.IO.FileNotFoundException> и выводит сообщение в консоль, если файл данных не найден. Следующий оператор `throw` создает новое исключение <xref:System.IO.FileNotFoundException> и добавляет в него текстовую информацию.

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>См. также  
[Исключения](index.md)
