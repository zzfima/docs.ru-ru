---
title: Практическое руководство. Выполнение базовых операций со строками в .NET
description: См. пример, который вызывает много строковых методов.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET Framework], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.custom: seodec18
ms.openlocfilehash: 9c5cdd15e189b8f0821f52d216c398299d44a5ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105739"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a>Практическое руководство. Выполнение базовых операций со строками в .NET
В следующем примере некоторые методы, описанные в руководстве по [базовым операциям со строками](../../../docs/standard/base-types/basic-string-operations.md), используются для создания класса, который выполняет обработку строк так же, как это происходит в реальном приложении. Класс `MailToData` хранит имя и адрес человека в отдельных свойствах и предоставляет способ объединения полей `City`, `State` и `Zip` в одну строку для отображения пользователю. Более того, данный класс позволяет пользователю вводить сведения о городе, области и почтовом индексе в одну строку. Приложение автоматически анализирует эту строку и вводит необходимые сведения в соответствующее свойство.  
  
 В этом упрощенном примере используется консольное приложение с интерфейсом командной строки.  
  
## <a name="example"></a>Пример  
 [!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
 [!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
 При выполнении предыдущего кода пользователю предлагается ввести его имя и адрес. Приложение размещает сведения в соответствующих свойствах и отображает их для пользователя, создавая одну строку, в которой представлены сведения о городе, области и почтовом индексе.  
  
## <a name="see-also"></a>См. также

- [Базовые операции со строками в .NET Framework](../../../docs/standard/base-types/basic-string-operations.md)
