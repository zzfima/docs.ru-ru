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
ms.openlocfilehash: a1a8658999f08d295e76afc9df6ec8acd146abe2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863230"
---
# <a name="how-to-explicitly-throw-exceptions"></a>Явное создание исключений

Исключение можно вызвать явным образом с помощью оператора `throw`. Перехваченное исключение можно вызвать повторно с помощью оператора `throw`. При написании кода рекомендуется добавлять сведения в исключение, которое выдается повторно, чтобы предоставить дополнительную информацию при отладке.

В следующем примере кода блок `try`/`catch` используется, чтобы перехватить возможное <xref:System.IO.FileNotFoundException>. После блока `try` находится блок `catch`, который перехватывает <xref:System.IO.FileNotFoundException> и выводит сообщение в консоль, если файл данных не найден. Следующий оператор `throw` создает новое исключение <xref:System.IO.FileNotFoundException> и добавляет в него текстовую информацию.

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a>См. также

- [Исключения](index.md)
