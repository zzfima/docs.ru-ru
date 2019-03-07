---
title: Метод ISymUnmanagedReader::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a5eb91d02ce55601f86dcadc744ef23ca430d9c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471697"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="e67c0-102">Метод ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="e67c0-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="e67c0-103">Инициализирует средство чтения символов с интерфейсом средства импорта метаданных, что средство чтения будет сопоставлено, а также имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="e67c0-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e67c0-104">Этот метод может вызываться только один раз и должен вызываться до всех остальных методов чтения.</span><span class="sxs-lookup"><span data-stu-id="e67c0-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67c0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e67c0-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e67c0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e67c0-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="e67c0-107">[in] Интерфейс импорта метаданных, с которым будет связано данное средство чтения.</span><span class="sxs-lookup"><span data-stu-id="e67c0-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="e67c0-108">[in] Имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="e67c0-108">[in] The file name of the module.</span></span> <span data-ttu-id="e67c0-109">Можно использовать `pIStream` параметра вместо этого.</span><span class="sxs-lookup"><span data-stu-id="e67c0-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="e67c0-110">[in] Путь для поиска.</span><span class="sxs-lookup"><span data-stu-id="e67c0-110">[in] The path to search.</span></span> <span data-ttu-id="e67c0-111">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e67c0-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="e67c0-112">[in] Файловый поток, используемый в качестве альтернативы в параметре filename.</span><span class="sxs-lookup"><span data-stu-id="e67c0-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e67c0-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e67c0-113">Return Value</span></span>  
 <span data-ttu-id="e67c0-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="e67c0-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e67c0-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="e67c0-115">Remarks</span></span>  
 <span data-ttu-id="e67c0-116">Необходимо указать только один из `filename` или `pIStream` параметров, не оба.</span><span class="sxs-lookup"><span data-stu-id="e67c0-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="e67c0-117">Параметр `searchPath` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="e67c0-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e67c0-118">Требования</span><span class="sxs-lookup"><span data-stu-id="e67c0-118">Requirements</span></span>  
 <span data-ttu-id="e67c0-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e67c0-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67c0-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e67c0-120">See also</span></span>
- [<span data-ttu-id="e67c0-121">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="e67c0-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
