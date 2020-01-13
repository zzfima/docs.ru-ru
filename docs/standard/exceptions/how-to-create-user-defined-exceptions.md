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
ms.openlocfilehash: 6de00490a17fff005dd50a7acc5247089c073f68
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708879"
---
# <a name="how-to-create-user-defined-exceptions"></a><span data-ttu-id="127af-102">Создание пользовательских исключений</span><span class="sxs-lookup"><span data-stu-id="127af-102">How to create user-defined exceptions</span></span>

<span data-ttu-id="127af-103">Платформа .NET предоставляет иерархию классов исключений, производных от базового класса <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="127af-103">.NET provides a hierarchy of exception classes ultimately derived from the base class <xref:System.Exception>.</span></span> <span data-ttu-id="127af-104">Тем не менее, если ни одно из стандартных исключений не подходит, можно создать собственные классы исключений путем наследования от класса <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="127af-104">However, if none of the predefined exceptions meets your needs, you can create your own exception classes by deriving from the <xref:System.Exception> class.</span></span>

<span data-ttu-id="127af-105">При создании собственных исключений заканчивайте имя класса пользовательского исключения словом Exception и реализуйте три общих конструктора, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="127af-105">When creating your own exceptions, end the class name of the user-defined exception with the word "Exception", and implement the three common constructors, as shown in the following example.</span></span> <span data-ttu-id="127af-106">В примере определяется новый класс исключений `EmployeeListNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="127af-106">The example defines a new exception class named `EmployeeListNotFoundException`.</span></span> <span data-ttu-id="127af-107">Этот класс является производным от <xref:System.Exception> и включает три конструктора.</span><span class="sxs-lookup"><span data-stu-id="127af-107">The class is derived from <xref:System.Exception> and includes three constructors.</span></span>

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> <span data-ttu-id="127af-108">В ситуациях, когда используется удаленное взаимодействие, необходимо убедиться, что метаданные для пользовательского исключения доступны на сервере (вызываемый объект) и для клиента (прокси-объект или вызывающий объект).</span><span class="sxs-lookup"><span data-stu-id="127af-108">In situations where you are using remoting, you must ensure that the metadata for any user-defined exceptions is available at the server (callee) and to the client (the proxy object or caller).</span></span> <span data-ttu-id="127af-109">Дополнительные сведения см. в разделе [Лучшие методики обработки исключений](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="127af-109">For more information, see [Best practices for exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="127af-110">См. также</span><span class="sxs-lookup"><span data-stu-id="127af-110">See also</span></span>

- [<span data-ttu-id="127af-111">Исключения</span><span class="sxs-lookup"><span data-stu-id="127af-111">Exceptions</span></span>](index.md)
