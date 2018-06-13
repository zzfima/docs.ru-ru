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
ms.openlocfilehash: 7b4c334d82320066bf9459907660fe6b7e2acefd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425325"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="53161-102">Метод ISymUnmanagedReader::GetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="53161-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="53161-103">Возвращает метод, заданный в качестве точки входа пользователя для модуля, если таковые имеются.</span><span class="sxs-lookup"><span data-stu-id="53161-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="53161-104">Например этот метод может быть основного метода пользователя, а не созданные компилятором заглушки перед основным методом.</span><span class="sxs-lookup"><span data-stu-id="53161-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53161-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53161-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53161-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="53161-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="53161-107">[out] Указатель на переменную, которая получает точку входа.</span><span class="sxs-lookup"><span data-stu-id="53161-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53161-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="53161-108">Return Value</span></span>  
 <span data-ttu-id="53161-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="53161-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53161-110">Требования</span><span class="sxs-lookup"><span data-stu-id="53161-110">Requirements</span></span>  
 <span data-ttu-id="53161-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="53161-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53161-112">См. также</span><span class="sxs-lookup"><span data-stu-id="53161-112">See Also</span></span>  
 [<span data-ttu-id="53161-113">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="53161-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
