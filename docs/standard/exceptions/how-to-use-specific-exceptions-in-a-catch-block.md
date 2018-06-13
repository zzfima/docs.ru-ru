---
title: Практическое руководство. Использование определенных исключений в блоке Catch
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 424db46c879974a9859637f9a2a5dfcd4494a3c5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571802"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a>Практическое руководство. Использование определенных исключений в блоке catch

В общем случае вместо использования базового оператора `catch` рекомендуется перехватывать исключения определенного типа.

При возникновении исключения оно передается вверх по стеку, и каждый блок catch получает возможность обработать его. Важен порядок операторов catch. Размещайте блоки catch, предназначенные для определенных исключений, до общего блока перехвата исключений. В противном случае компилятор может выдать ошибку. Соответствующий блок catch определяется путем соотнесения типа исключения с именем исключения, указанным в блоке catch. Когда специальный блок catch отсутствует, исключение перехватывается общим блоком catch, если он существует.

В следующем примере кода блок `try`/`catch` используется, чтобы перехватить <xref:System.InvalidCastException>. В примере создается класс `Employee` с единственным свойством — уровнем сотрудника (`Emlevel`). Метод `PromoteEmployee` принимает объект и повышает уровень сотрудника. Исключение <xref:System.InvalidCastException> возникает, когда в метод `PromoteEmployee` передается экземпляр <xref:System.DateTime>.

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)] 

## <a name="see-also"></a>См. также  
[Исключения](index.md)
