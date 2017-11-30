---
title: "Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68c5d6662d8cbecca06268bd5010878c4e476f47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="b1f76-102">Метод ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="b1f76-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="b1f76-103">Задает начальный метод, который инициирует асинхронную операцию.</span><span class="sxs-lookup"><span data-stu-id="b1f76-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1f76-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1f76-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1f76-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1f76-105">Parameters</span></span>  
  
|<span data-ttu-id="b1f76-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="b1f76-106">Parameter</span></span>|<span data-ttu-id="b1f76-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b1f76-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="b1f76-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b1f76-108">Return Value</span></span>  
 <span data-ttu-id="b1f76-109">Возвращает `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="b1f76-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1f76-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b1f76-110">Requirements</span></span>  
 <span data-ttu-id="b1f76-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b1f76-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1f76-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b1f76-112">See Also</span></span>  
 [<span data-ttu-id="b1f76-113">Интерфейс ISymUnmanagedAsyncMethodPropertiesWriter</span><span class="sxs-lookup"><span data-stu-id="b1f76-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
