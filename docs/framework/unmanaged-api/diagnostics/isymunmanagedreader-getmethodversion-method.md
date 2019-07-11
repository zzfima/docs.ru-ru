---
title: Метод ISymUnmanagedReader::GetMethodVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodVersion
helpviewer_keywords:
- GetMethodVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodVersion method [.NET Framework debugging]
ms.assetid: d6f9ac84-302a-4f5e-b990-e76f4269fceb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f45423bb0ff4c755e657729c5725c8d9a22bde3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746763"
---
# <a name="isymunmanagedreadergetmethodversion-method"></a><span data-ttu-id="e58a5-102">Метод ISymUnmanagedReader::GetMethodVersion</span><span class="sxs-lookup"><span data-stu-id="e58a5-102">ISymUnmanagedReader::GetMethodVersion Method</span></span>
<span data-ttu-id="e58a5-103">Получает версию метода.</span><span class="sxs-lookup"><span data-stu-id="e58a5-103">Gets the method version.</span></span> <span data-ttu-id="e58a5-104">Версия метода начинается с 1 и увеличивается каждый раз, когда метод компилируется.</span><span class="sxs-lookup"><span data-stu-id="e58a5-104">The method version starts at 1 and is incremented each time the method is recompiled.</span></span> <span data-ttu-id="e58a5-105">Перекомпиляция может происходить без изменения в метод.</span><span class="sxs-lookup"><span data-stu-id="e58a5-105">Recompilation can happen without changes to the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e58a5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e58a5-106">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodVersion (  
    [in]  ISymUnmanagedMethod* pMethod,  
    [out] int* version);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e58a5-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e58a5-107">Parameters</span></span>  
 `pMethod`  
 <span data-ttu-id="e58a5-108">[in] Метод, для которого необходимо получить версию.</span><span class="sxs-lookup"><span data-stu-id="e58a5-108">[in] The method for which to get the version.</span></span>  
  
 `version`  
 <span data-ttu-id="e58a5-109">[out] Указатель на переменную, которая получает версию метода.</span><span class="sxs-lookup"><span data-stu-id="e58a5-109">[out] A pointer to a variable that receives the method version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e58a5-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e58a5-110">Return Value</span></span>  
 <span data-ttu-id="e58a5-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="e58a5-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e58a5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e58a5-112">Requirements</span></span>  
 <span data-ttu-id="e58a5-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e58a5-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e58a5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e58a5-114">See also</span></span>

- [<span data-ttu-id="e58a5-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="e58a5-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
