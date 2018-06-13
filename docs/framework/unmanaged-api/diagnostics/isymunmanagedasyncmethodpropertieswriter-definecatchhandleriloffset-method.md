---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce462c4e7e9c8fb11ee74a91f3ece2465a44a834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425435"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="4a742-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="4a742-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="4a742-103">Задает смещение для обработчика catch, созданный компилятором, являющийся оболочкой для асинхронного метода на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="4a742-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="4a742-104">Смещение на промежуточном Языке созданный catch используется отладчиком для обработки catch, как если бы не написанный пользователем, несмотря на то, что она может возникать в метода кода пользователя.</span><span class="sxs-lookup"><span data-stu-id="4a742-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="4a742-105">В частности, он используется в ответ на **CatchHandlerFound** события исключения.</span><span class="sxs-lookup"><span data-stu-id="4a742-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a742-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a742-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4a742-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a742-107">Parameters</span></span>  
  
|<span data-ttu-id="4a742-108">Параметр</span><span class="sxs-lookup"><span data-stu-id="4a742-108">Parameter</span></span>|<span data-ttu-id="4a742-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4a742-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="4a742-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a742-110">Return Value</span></span>  
 <span data-ttu-id="4a742-111">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="4a742-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a742-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4a742-112">Requirements</span></span>  
 <span data-ttu-id="4a742-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4a742-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a742-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4a742-114">See Also</span></span>  
 [<span data-ttu-id="4a742-115">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="4a742-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
