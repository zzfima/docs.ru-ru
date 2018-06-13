---
title: Метод ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82e657e91e586d7fe409646ea4fb8946c026e84c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424343"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="5d6c9-102">Метод ISymUnmanagedENCUpdate::GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="5d6c9-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="5d6c9-103">Возвращает локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="5d6c9-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d6c9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d6c9-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d6c9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d6c9-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="5d6c9-106">[in] Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="5d6c9-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="5d6c9-107">[in] Объект `ULONG` указывает размер `rgLocals` параметра.</span><span class="sxs-lookup"><span data-stu-id="5d6c9-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="5d6c9-108">[out] Возвращаемый массив <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable` экземпляров.</span><span class="sxs-lookup"><span data-stu-id="5d6c9-108">[out] The returned array of <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable`  instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5d6c9-109">[out] Указатель на `ULONG` , получающий размер `rgLocals` буфера, должны содержать локальные переменные.</span><span class="sxs-lookup"><span data-stu-id="5d6c9-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d6c9-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5d6c9-110">Return Value</span></span>  
 <span data-ttu-id="5d6c9-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="5d6c9-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d6c9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="5d6c9-112">Requirements</span></span>  
 <span data-ttu-id="5d6c9-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5d6c9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6c9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5d6c9-114">See Also</span></span>  
 [<span data-ttu-id="5d6c9-115">Интерфейс ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="5d6c9-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
