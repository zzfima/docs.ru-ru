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
ms.openlocfilehash: 48b450e579263876725f96e0adfc4c16aac1d869
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160161"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a>Практическое руководство. Использование определенных исключений в блоке catch

В общем случае вместо использования базового оператора `catch` рекомендуется перехватывать исключения определенного типа.

При возникновении исключения оно передается вверх по стеку, и каждый блок catch получает возможность обработать его. Важен порядок операторов catch. Размещайте блоки catch, предназначенные для определенных исключений, до общего блока перехвата исключений. В противном случае компилятор может выдать ошибку. Соответствующий блок catch определяется путем соотнесения типа исключения с именем исключения, указанным в блоке catch. Когда специальный блок catch отсутствует, исключение перехватывается общим блоком catch, если он существует.

В следующем примере кода блок `try`/`catch` используется, чтобы перехватить <xref:System.InvalidCastException>. В примере создается класс `Employee` с единственным свойством — уровнем сотрудника (`Emlevel`). Метод `PromoteEmployee` принимает объект и повышает уровень сотрудника. Исключение <xref:System.InvalidCastException> возникает, когда в метод <xref:System.DateTime> передается экземпляр `PromoteEmployee`.

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]

## <a name="see-also"></a>См. также раздел

- [Исключения](index.md)
