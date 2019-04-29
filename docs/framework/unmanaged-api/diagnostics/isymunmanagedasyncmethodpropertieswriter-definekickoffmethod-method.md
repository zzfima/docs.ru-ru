---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce3c135e031d0c8425e990811fedc40f4ec45243
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940118"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="a017e-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="a017e-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="a017e-103">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="a017e-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a017e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a017e-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a017e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a017e-105">Parameters</span></span>  
  
|<span data-ttu-id="a017e-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="a017e-106">Parameter</span></span>|<span data-ttu-id="a017e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a017e-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="a017e-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a017e-108">Return Value</span></span>  
 <span data-ttu-id="a017e-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="a017e-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a017e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a017e-110">Requirements</span></span>  
 <span data-ttu-id="a017e-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a017e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a017e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a017e-112">See also</span></span>

- [<span data-ttu-id="a017e-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="a017e-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
