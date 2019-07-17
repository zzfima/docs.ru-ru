---
title: Практическое руководство. Создание пользовательских исключений
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42860f549877436f43bfdc20fb3abde91d36101d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783191"
---
# <a name="how-to-create-user-defined-exceptions"></a>Создание пользовательских исключений

Платформа .NET предоставляет иерархию классов исключений, производных от базового класса <xref:System.Exception>. Тем не менее, если ни одно из стандартных исключений не подходит, можно создать собственные классы исключений путем наследования от класса <xref:System.Exception>.

При создании собственных исключений заканчивайте имя класса пользовательского исключения словом Exception и реализуйте три общих конструктора, как показано в следующем примере. В примере определяется новый класс исключений `EmployeeListNotFoundException`. Этот класс является производным от <xref:System.Exception> и включает три конструктора.

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> В ситуациях, когда используется удаленное взаимодействие, необходимо убедиться, что метаданные для пользовательского исключения доступны на сервере (вызываемый объект) и для клиента (прокси-объект или вызывающий объект). Дополнительные сведения см. в разделе [Лучшие методики обработки исключений](best-practices-for-exceptions.md).

## <a name="see-also"></a>См. также

- [Исключения](index.md)
