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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0739cc38d1f12967f0daef2d6828e04a256ade6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59201849"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="ebea6-102">Метод ISymUnmanagedWriter::UsingNamespace</span><span class="sxs-lookup"><span data-stu-id="ebea6-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="ebea6-103">Указывает, что данное имя полного пространства имен используется в текущей открытой лексической области.</span><span class="sxs-lookup"><span data-stu-id="ebea6-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="ebea6-104">Пространство имен будет использоваться во всех областях, которые наследуют из открытых области.</span><span class="sxs-lookup"><span data-stu-id="ebea6-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="ebea6-105">Закрытие текущей области также приведет к остановке использования пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ebea6-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebea6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebea6-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebea6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebea6-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="ebea6-108">[in] Указатель на полное имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ebea6-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ebea6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ebea6-109">Return Value</span></span>  
 <span data-ttu-id="ebea6-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ebea6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebea6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ebea6-111">Requirements</span></span>  
 <span data-ttu-id="ebea6-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ebea6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebea6-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ebea6-113">See also</span></span>

- [<span data-ttu-id="ebea6-114">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ebea6-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
