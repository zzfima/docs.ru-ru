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
ms.openlocfilehash: 11dc050e2fe16a64db4ac95bb1386e2d90535e81
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895021"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="d15bb-102">Метод ISymUnmanagedWriter::SetUserEntryPoint</span><span class="sxs-lookup"><span data-stu-id="d15bb-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="d15bb-103">Задает определяемый пользователем метод, являющийся точкой входа для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="d15bb-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="d15bb-104">Например, эта точка входа может быть основным методом пользователя вместо заглушек, созданной компилятором до Main.</span><span class="sxs-lookup"><span data-stu-id="d15bb-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d15bb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d15bb-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d15bb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d15bb-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="d15bb-107">окне Токен метаданных для метода, который является точкой входа пользователя.</span><span class="sxs-lookup"><span data-stu-id="d15bb-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d15bb-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d15bb-108">Return Value</span></span>  
 <span data-ttu-id="d15bb-109">Значение S_OK, если метод выполнен. в противном случае — E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="d15bb-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d15bb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d15bb-110">Requirements</span></span>  
 <span data-ttu-id="d15bb-111">**Заголовок.** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="d15bb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15bb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="d15bb-112">See also</span></span>

- [<span data-ttu-id="d15bb-113">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="d15bb-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
