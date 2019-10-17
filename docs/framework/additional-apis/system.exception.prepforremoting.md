---
title: Метод Exception. Препфорремотинг (система)
author: mairaw
ms.author: mairaw
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 057390d64f70d3cb8eba7d4b29b94570fdca77e3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72405900"
---
# <a name="exceptionprepforremoting-method"></a><span data-ttu-id="b8c7c-102">Метод Exception. Препфорремотинг</span><span class="sxs-lookup"><span data-stu-id="b8c7c-102">Exception.PrepForRemoting Method</span></span>

<span data-ttu-id="b8c7c-103">Сохраняет трассировку стека на стороне сервера, добавляя ее к сообщению, прежде чем исключение будет повторно создано на сайте вызова клиента.</span><span class="sxs-lookup"><span data-stu-id="b8c7c-103">Preserves the server-side stack trace by appending it to the message before the exception is rethrown at the client call site.</span></span>

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a><span data-ttu-id="b8c7c-104">Returns</span><span class="sxs-lookup"><span data-stu-id="b8c7c-104">Returns</span></span>

<xref:System.Exception>  
<span data-ttu-id="b8c7c-105">Данный экземпляр <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="b8c7c-105">This <xref:System.Exception> instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8c7c-106">Заметки</span><span class="sxs-lookup"><span data-stu-id="b8c7c-106">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="b8c7c-107">Метод `Exception.PrepForRemoting` является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="b8c7c-107">The `Exception.PrepForRemoting` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="b8c7c-108">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="b8c7c-108">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8c7c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b8c7c-109">Requirements</span></span>

<span data-ttu-id="b8c7c-110">**Пространство имен:** <xref:System></span><span class="sxs-lookup"><span data-stu-id="b8c7c-110">**Namespace:** <xref:System></span></span>

<span data-ttu-id="b8c7c-111">**Сборка:** mscorlib. dll (в mscorlib. dll)</span><span class="sxs-lookup"><span data-stu-id="b8c7c-111">**Assembly:** mscorlib.dll (in mscorlib.dll)</span></span>

<span data-ttu-id="b8c7c-112">**.NET Framework версии:** Доступно с 1,0.</span><span class="sxs-lookup"><span data-stu-id="b8c7c-112">**.NET Framework versions:** Available since 1.0.</span></span>
