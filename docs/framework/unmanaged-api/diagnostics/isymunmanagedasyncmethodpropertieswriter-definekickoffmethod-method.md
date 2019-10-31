---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: ccf1287a1b0218e7f2560e1afbb0930c93b43263
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129177"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="0c0a4-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="0c0a4-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="0c0a4-103">Задает начальный метод, инициирующий асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="0c0a4-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c0a4-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c0a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c0a4-105">Parameters</span></span>  
  
|<span data-ttu-id="0c0a4-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="0c0a4-106">Parameter</span></span>|<span data-ttu-id="0c0a4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0c0a4-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="0c0a4-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0c0a4-108">Return Value</span></span>  
 <span data-ttu-id="0c0a4-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="0c0a4-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c0a4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0c0a4-110">Requirements</span></span>  
 <span data-ttu-id="0c0a4-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="0c0a4-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0a4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0c0a4-112">See also</span></span>

- [<span data-ttu-id="0c0a4-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="0c0a4-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
