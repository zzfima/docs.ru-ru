---
title: Метод ISymUnmanagedWriter::UsingNamespace
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
ms.openlocfilehash: cb0af78092822875204f45ec3dca1484e5b5fc90
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427467"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="fc972-102">Метод ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="fc972-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="fc972-103">Указывает, что данное полное имя пространства имен используется в открытой лексической области.</span><span class="sxs-lookup"><span data-stu-id="fc972-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="fc972-104">Пространство имен будет использоваться во всех областях, наследующих от текущей открытой области.</span><span class="sxs-lookup"><span data-stu-id="fc972-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="fc972-105">Закрытие текущей области также приведет к отмене использования пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fc972-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc972-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc972-106">Syntax</span></span>  
  
```cpp  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc972-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc972-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="fc972-108">окне Указатель на полное имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="fc972-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc972-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc972-109">Return Value</span></span>  
 <span data-ttu-id="fc972-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="fc972-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc972-111">Требования</span><span class="sxs-lookup"><span data-stu-id="fc972-111">Requirements</span></span>  
 <span data-ttu-id="fc972-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="fc972-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc972-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="fc972-113">See also</span></span>

- [<span data-ttu-id="fc972-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="fc972-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
