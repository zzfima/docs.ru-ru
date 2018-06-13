---
title: Метод ISymENCUnmanagedMethod::GetFileNameFromOffset
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db3e9cfa73672920ff70d9128541a8f513fca00f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432660"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="6aa34-102">Метод ISymENCUnmanagedMethod::GetFileNameFromOffset</span><span class="sxs-lookup"><span data-stu-id="6aa34-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="6aa34-103">Получает имя файла для строки, связанной со смещением.</span><span class="sxs-lookup"><span data-stu-id="6aa34-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6aa34-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6aa34-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6aa34-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="6aa34-106">[in] Объект `ULONG32` , содержащий смещение.</span><span class="sxs-lookup"><span data-stu-id="6aa34-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6aa34-107">[in] Объект `ULONG32` указывает размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="6aa34-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6aa34-108">[out] Указатель на `ULONG32` , получающий размер в символах, буфера, необходимый для хранения имен файлов.</span><span class="sxs-lookup"><span data-stu-id="6aa34-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="6aa34-109">[out] Буфер, содержащий имена файлов.</span><span class="sxs-lookup"><span data-stu-id="6aa34-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6aa34-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6aa34-110">Return Value</span></span>  
 <span data-ttu-id="6aa34-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="6aa34-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa34-112">Требования</span><span class="sxs-lookup"><span data-stu-id="6aa34-112">Requirements</span></span>  
 <span data-ttu-id="6aa34-113">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6aa34-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa34-114">См. также</span><span class="sxs-lookup"><span data-stu-id="6aa34-114">See Also</span></span>  
 [<span data-ttu-id="6aa34-115">Интерфейс ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="6aa34-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
