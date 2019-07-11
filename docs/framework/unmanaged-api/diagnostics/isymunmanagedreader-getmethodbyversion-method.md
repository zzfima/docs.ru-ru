---
title: Метод ISymUnmanagedReader::GetMethodByVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f3210f0186401729a5bc95369e88b290ae49a634
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776989"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a><span data-ttu-id="10c18-102">Метод ISymUnmanagedReader::GetMethodByVersion</span><span class="sxs-lookup"><span data-stu-id="10c18-102">ISymUnmanagedReader::GetMethodByVersion Method</span></span>
<span data-ttu-id="10c18-103">Получает метода средства чтения символов, получив токен метода и номеру версии редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="10c18-103">Gets a symbol reader method, given a method token and an edit-and-copy version number.</span></span> <span data-ttu-id="10c18-104">Номера версий начинаются с 1 и увеличивается каждый раз, когда метод изменяется в результате операции редактирования и копирования.</span><span class="sxs-lookup"><span data-stu-id="10c18-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c18-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10c18-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10c18-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="10c18-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="10c18-107">[in] Маркер метода.</span><span class="sxs-lookup"><span data-stu-id="10c18-107">[in] The method token.</span></span>  
  
 `version`  
 <span data-ttu-id="10c18-108">[in] Версия метода.</span><span class="sxs-lookup"><span data-stu-id="10c18-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="10c18-109">[out] Указатель на возвращенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="10c18-109">[out] A pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10c18-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="10c18-110">Return Value</span></span>  
 <span data-ttu-id="10c18-111">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="10c18-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c18-112">Требования</span><span class="sxs-lookup"><span data-stu-id="10c18-112">Requirements</span></span>  
 <span data-ttu-id="10c18-113">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10c18-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c18-114">См. также</span><span class="sxs-lookup"><span data-stu-id="10c18-114">See also</span></span>

- [<span data-ttu-id="10c18-115">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="10c18-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
