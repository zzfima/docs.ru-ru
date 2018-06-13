---
title: Метод ISymUnmanagedSourceServerModule::GetSourceServerData
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: afc041896615e906ac49eed9a7be139dff217463
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427015"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="ed07a-102">Метод ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="ed07a-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="ed07a-103">Возвращает данные исходного сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="ed07a-103">Returns the source server data for the module.</span></span> <span data-ttu-id="ed07a-104">Вызывающий объект должен освободить ресурсы с помощью `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="ed07a-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed07a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ed07a-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed07a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ed07a-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="ed07a-107">[out] Указатель на `ULONG32` , получающий размер в байтах данных с исходного сервера.</span><span class="sxs-lookup"><span data-stu-id="ed07a-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="ed07a-108">[out] Указатель на возвращаемый `pDataByteCount` значение.</span><span class="sxs-lookup"><span data-stu-id="ed07a-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed07a-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ed07a-109">Return Value</span></span>  
 <span data-ttu-id="ed07a-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="ed07a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed07a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ed07a-111">Requirements</span></span>  
 <span data-ttu-id="ed07a-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ed07a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed07a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ed07a-113">See Also</span></span>  
 [<span data-ttu-id="ed07a-114">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="ed07a-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
