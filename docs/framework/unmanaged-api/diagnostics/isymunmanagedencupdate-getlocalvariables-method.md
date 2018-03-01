---
title: "Метод ISymUnmanagedENCUpdate::GetLocalVariables"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eefd64441221a7e6e00689d6be272540f9c2423c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="1eda2-102">Метод ISymUnmanagedENCUpdate::GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="1eda2-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="1eda2-103">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="1eda2-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eda2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1eda2-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1eda2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1eda2-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="1eda2-106">[in] Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="1eda2-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="1eda2-107">[in] Объект `ULONG` указывает размер `rgLocals` параметра.</span><span class="sxs-lookup"><span data-stu-id="1eda2-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="1eda2-108">[out] Возвращаемый массив <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="1eda2-108">[out] The returned array of <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable`  instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1eda2-109">[out] Указатель на `ULONG` , получающий размер `rgLocals` буфера, должны содержать локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="1eda2-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1eda2-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1eda2-110">Return Value</span></span>  
 <span data-ttu-id="1eda2-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="1eda2-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eda2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1eda2-112">Requirements</span></span>  
 <span data-ttu-id="1eda2-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1eda2-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eda2-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1eda2-114">See Also</span></span>  
 [<span data-ttu-id="1eda2-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="1eda2-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
