---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b4564aeb3c8ed4674e755e5691bb0a9d417bca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624199"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="9a2a2-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="9a2a2-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="9a2a2-103">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="9a2a2-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a2a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a2a2-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a2a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a2a2-105">Parameters</span></span>  
  
|<span data-ttu-id="9a2a2-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="9a2a2-106">Parameter</span></span>|<span data-ttu-id="9a2a2-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9a2a2-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="9a2a2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9a2a2-108">Return Value</span></span>  
 <span data-ttu-id="9a2a2-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="9a2a2-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a2a2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9a2a2-110">Requirements</span></span>  
 <span data-ttu-id="9a2a2-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a2a2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a2a2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9a2a2-112">See also</span></span>
- [<span data-ttu-id="9a2a2-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="9a2a2-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
