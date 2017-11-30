---
title: "Метод ISymUnmanagedReader::GetSymbolStoreFileName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymbolStoreFileName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 951dfd45f6b313b6cde28f3f65f2799380a33a78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="5cc05-102">Метод ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="5cc05-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="5cc05-103">Задает имя файла на диске в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="5cc05-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cc05-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5cc05-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5cc05-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5cc05-106">[in] Размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="5cc05-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5cc05-107">[out] Указатель на переменную, которая получает длину имени, возвращаемого в `szName`, включая нулем.</span><span class="sxs-lookup"><span data-stu-id="5cc05-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="5cc05-108">[out] Указатель на переменную, которая получает имя файла в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="5cc05-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cc05-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5cc05-109">Return Value</span></span>  
 <span data-ttu-id="5cc05-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="5cc05-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc05-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5cc05-111">Requirements</span></span>  
 <span data-ttu-id="5cc05-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5cc05-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc05-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5cc05-113">See Also</span></span>  
 [<span data-ttu-id="5cc05-114">ISymUnmanagedReader-интерфейс</span><span class="sxs-lookup"><span data-stu-id="5cc05-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
