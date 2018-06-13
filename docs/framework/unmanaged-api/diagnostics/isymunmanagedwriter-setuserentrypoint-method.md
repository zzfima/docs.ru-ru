---
title: Метод ISymUnmanagedWriter::SetUserEntryPoint
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ec44d4c2757555c74fe7fc27c26cc5fc87c4517
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426691"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="b887f-102">Метод ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="b887f-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="b887f-103">Задает пользовательский метод, являющегося точкой входа для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="b887f-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="b887f-104">Например эта точка входа может быть основным методом пользователя вместо созданных компилятором заглушек перед основным.</span><span class="sxs-lookup"><span data-stu-id="b887f-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b887f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b887f-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b887f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b887f-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="b887f-107">[in] Токен метаданных для метода, который является входа пользователя точки.</span><span class="sxs-lookup"><span data-stu-id="b887f-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b887f-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b887f-108">Return Value</span></span>  
 <span data-ttu-id="b887f-109">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b887f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b887f-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b887f-110">Requirements</span></span>  
 <span data-ttu-id="b887f-111">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b887f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b887f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b887f-112">See Also</span></span>  
 [<span data-ttu-id="b887f-113">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="b887f-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
