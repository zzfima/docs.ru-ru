---
title: Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 8b38973e4cb2c83ce32b8a08e54d828a8eeef879
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039537"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="81928-102">Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом</span><span class="sxs-lookup"><span data-stu-id="81928-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>

<span data-ttu-id="81928-103">В этом примере создается экземпляр глобального прокси-сервера, который позволяет любому <xref:System.Net.WebRequest> использовать прокси-сервер для связи с Интернетом.</span><span class="sxs-lookup"><span data-stu-id="81928-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="81928-104">В этом примере предполагается, что сервер имеет имя `webproxy` и подключается к стандартному HTTP-порту 80.</span><span class="sxs-lookup"><span data-stu-id="81928-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>

## <a name="example"></a><span data-ttu-id="81928-105">Пример</span><span class="sxs-lookup"><span data-stu-id="81928-105">Example</span></span>

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a><span data-ttu-id="81928-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="81928-106">Compiling the Code</span></span>

<span data-ttu-id="81928-107">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="81928-107">This example requires:</span></span>

- <span data-ttu-id="81928-108">[Директива C# `using`](../../csharp/language-reference/keywords/using-directive.md) для пространства имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="81928-108">A C# [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>
- <span data-ttu-id="81928-109">[Инструкция Visual Basic `Imports`](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для пространств имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="81928-109">A Visual Basic [`Imports` statement](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) for the **System.Net** namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="81928-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81928-110">See also</span></span>

- [<span data-ttu-id="81928-111">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="81928-111">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="81928-112">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="81928-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
