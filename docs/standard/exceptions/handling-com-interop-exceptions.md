---
title: "Обработка исключений COM-взаимодействия"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: error-reference
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e894d07e77b929b1ea22df2d34e542544ec3b1f3
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="handling-com-interop-exceptions"></a><span data-ttu-id="bda10-102">Обработка исключений COM-взаимодействия</span><span class="sxs-lookup"><span data-stu-id="bda10-102">Handling COM Interop Exceptions</span></span>
<span data-ttu-id="bda10-103">При обработке исключений управляемый и неуправляемый код может работать совместно.</span><span class="sxs-lookup"><span data-stu-id="bda10-103">Managed and unmanaged code can work together to handle exceptions.</span></span> <span data-ttu-id="bda10-104">Если метод вызывает исключение в управляемом коде, то среда CLR может передать значение HRESULT в COM-объект.</span><span class="sxs-lookup"><span data-stu-id="bda10-104">If a method throws an exception in managed code, the common language runtime can pass an HRESULT to a COM object.</span></span> <span data-ttu-id="bda10-105">Если сбой метода происходит в неуправляемом коде и возвращается значение HRESULT, указывающее на сбой, то среда выполнения создает исключение, которое может быть перехвачено управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="bda10-105">If a method fails in unmanaged code by returning a failure HRESULT, the runtime throws an exception that can be caught by managed code.</span></span>  
  
 <span data-ttu-id="bda10-106">Среда выполнения автоматически сопоставляет значение HRESULT из COM-взаимодействия с более конкретными исключениями.</span><span class="sxs-lookup"><span data-stu-id="bda10-106">The runtime automatically maps the HRESULT from COM interop to more specific exceptions.</span></span> <span data-ttu-id="bda10-107">Например, E_ACCESSDENIED становится <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY становится <xref:System.OutOfMemoryException> и т. д.</span><span class="sxs-lookup"><span data-stu-id="bda10-107">For example, E_ACCESSDENIED becomes <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY becomes <xref:System.OutOfMemoryException>, and so on.</span></span>  
  
 <span data-ttu-id="bda10-108">Если значение HRESULT является пользовательским результатом или неизвестно среде выполнения, то она передает клиенту универсальное исключение <xref:System.Runtime.InteropServices.COMException>.</span><span class="sxs-lookup"><span data-stu-id="bda10-108">If the HRESULT is a custom result or if it is unknown to the runtime, the runtime passes a generic <xref:System.Runtime.InteropServices.COMException> to the client.</span></span> <span data-ttu-id="bda10-109">Свойство **ErrorCode** исключения **COMException** содержит значение HRESULT.</span><span class="sxs-lookup"><span data-stu-id="bda10-109">The **ErrorCode** property of the **COMException** contains the HRESULT value.</span></span>  
  
## <a name="working-with-ierrorinfo"></a><span data-ttu-id="bda10-110">Работа с IErrorInfo</span><span class="sxs-lookup"><span data-stu-id="bda10-110">Working with IErrorInfo</span></span>  
 <span data-ttu-id="bda10-111">При передаче ошибки из COM в управляемый код среда выполнения заносит в объект исключения сведения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="bda10-111">When an error is passed from COM to managed code, the runtime populates the exception object with error information.</span></span> <span data-ttu-id="bda10-112">COM-объекты, поддерживающие IErrorInfo и возвращающие HRESULTS, предоставляют эти сведения в исключения управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bda10-112">COM objects that support IErrorInfo and return HRESULTS provide this information to managed code exceptions.</span></span> <span data-ttu-id="bda10-113">Например, среда выполнения сопоставляет описание из ошибки COM со свойством <xref:System.Exception.Message%2A> исключения.</span><span class="sxs-lookup"><span data-stu-id="bda10-113">For example, the runtime maps the Description from the COM error to the exception's <xref:System.Exception.Message%2A> property.</span></span> <span data-ttu-id="bda10-114">Если HRESULT не предоставляет дополнительных сведений об ошибке, то среда выполнения заполняет значительную часть свойств исключения значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bda10-114">If the HRESULT provides no additional error information, the runtime fills many of the exception's properties with default values.</span></span>  
  
 <span data-ttu-id="bda10-115">Если сбой метода произошел в неуправляемом коде, то исключение может быть передано в сегмент управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="bda10-115">If a method fails in unmanaged code, an exception can be passed to a managed code segment.</span></span> <span data-ttu-id="bda10-116">В разделе [Сопоставление значений HRESULT и исключений](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) представлена таблица, в которой показано сопоставление значений HRESULT с объектами исключений среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="bda10-116">The topic [HRESULTS and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) contains a table showing how HRESULTS map to runtime exception objects.</span></span>  

## <a name="see-also"></a><span data-ttu-id="bda10-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bda10-117">See Also</span></span>
[<span data-ttu-id="bda10-118">Исключения</span><span class="sxs-lookup"><span data-stu-id="bda10-118">Exceptions</span></span>](index.md) 
