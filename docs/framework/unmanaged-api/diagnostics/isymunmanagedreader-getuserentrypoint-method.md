---
title: Метод ISymUnmanagedReader::GetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea0cba1f1b9154ccb14d75f7c377a8153c24f2b0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57499496"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="8f7c2-102">Метод ISymUnmanagedReader::GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="8f7c2-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="8f7c2-103">Возвращает метод, который был указан в качестве точки входа пользователя для модуля, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="8f7c2-104">Например этот метод может быть основной метод пользователя, а не созданные компилятором заглушки перед основным методом.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7c2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f7c2-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7c2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f7c2-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="8f7c2-107">[out] Указатель на переменную, которая получает точку входа.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8f7c2-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8f7c2-108">Return Value</span></span>  
 <span data-ttu-id="8f7c2-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7c2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8f7c2-110">Requirements</span></span>  
 <span data-ttu-id="8f7c2-111">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8f7c2-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7c2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8f7c2-112">See also</span></span>
- [<span data-ttu-id="8f7c2-113">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="8f7c2-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
