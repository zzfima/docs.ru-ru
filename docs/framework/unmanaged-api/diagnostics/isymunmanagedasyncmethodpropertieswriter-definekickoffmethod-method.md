---
title: Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a476d92486d7f2523dfbcc8b25e9c11e26c55f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425619"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="aa71a-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="aa71a-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="aa71a-103">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="aa71a-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa71a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa71a-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa71a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="aa71a-105">Parameters</span></span>  
  
|<span data-ttu-id="aa71a-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="aa71a-106">Parameter</span></span>|<span data-ttu-id="aa71a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="aa71a-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="aa71a-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="aa71a-108">Return Value</span></span>  
 <span data-ttu-id="aa71a-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="aa71a-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa71a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="aa71a-110">Requirements</span></span>  
 <span data-ttu-id="aa71a-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aa71a-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa71a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="aa71a-112">See Also</span></span>  
 [<span data-ttu-id="aa71a-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="aa71a-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
