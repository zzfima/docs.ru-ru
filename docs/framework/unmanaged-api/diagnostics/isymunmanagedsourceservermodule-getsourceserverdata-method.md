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
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176582"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="72504-102">Метод ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="72504-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="72504-103">Возвращает исходные данные сервера для модуля.</span><span class="sxs-lookup"><span data-stu-id="72504-103">Returns the source server data for the module.</span></span> <span data-ttu-id="72504-104">Звонящее должно освободить `CoTaskMemFree`ресурсы с помощью .</span><span class="sxs-lookup"><span data-stu-id="72504-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72504-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72504-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72504-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="72504-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="72504-107">(ваут) Указатель на `ULONG32` то, что получает размер, в байтах, данных исходного сервера.</span><span class="sxs-lookup"><span data-stu-id="72504-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="72504-108">(ваут) Указатель на возвращенное `pDataByteCount` значение.</span><span class="sxs-lookup"><span data-stu-id="72504-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72504-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="72504-109">Return Value</span></span>  
 <span data-ttu-id="72504-110">S_OK, если метод удается; в противном случае, E_FAIL или какой-либо другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="72504-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72504-111">Требования</span><span class="sxs-lookup"><span data-stu-id="72504-111">Requirements</span></span>  
 <span data-ttu-id="72504-112">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="72504-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72504-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="72504-113">See also</span></span>

- [<span data-ttu-id="72504-114">Интерфейс ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="72504-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
