---
title: "Метод ISymUnmanagedReader::Initialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.Initialize
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5917fbe3cebe9b1e9ab91d113aee2461f414c14d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="9cb69-102">Метод ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="9cb69-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="9cb69-103">Инициализирует средства чтения символов, при этом интерфейс импорта метаданных, данное средство чтения связанного с, а также имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="9cb69-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cb69-104">Этот метод может вызываться только один раз и должен вызываться до всех остальных методов чтения.</span><span class="sxs-lookup"><span data-stu-id="9cb69-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb69-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cb69-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9cb69-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9cb69-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="9cb69-107">[in] Интерфейс импорта метаданных, с которым будет связано данное средство чтения.</span><span class="sxs-lookup"><span data-stu-id="9cb69-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="9cb69-108">[in] Имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="9cb69-108">[in] The file name of the module.</span></span> <span data-ttu-id="9cb69-109">Можно использовать `pIStream` параметра вместо этого.</span><span class="sxs-lookup"><span data-stu-id="9cb69-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="9cb69-110">[in] Путь для поиска.</span><span class="sxs-lookup"><span data-stu-id="9cb69-110">[in] The path to search.</span></span> <span data-ttu-id="9cb69-111">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9cb69-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="9cb69-112">[in] Файловый поток, используемый вместо параметра filename.</span><span class="sxs-lookup"><span data-stu-id="9cb69-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cb69-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9cb69-113">Return Value</span></span>  
 <span data-ttu-id="9cb69-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="9cb69-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cb69-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cb69-115">Remarks</span></span>  
 <span data-ttu-id="9cb69-116">Необходимо указать только один из `filename` или `pIStream` параметров, не оба.</span><span class="sxs-lookup"><span data-stu-id="9cb69-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="9cb69-117">Параметр `searchPath` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9cb69-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cb69-118">Требования</span><span class="sxs-lookup"><span data-stu-id="9cb69-118">Requirements</span></span>  
 <span data-ttu-id="9cb69-119">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9cb69-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cb69-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9cb69-120">See Also</span></span>  
 [<span data-ttu-id="9cb69-121">ISymUnmanagedReader-интерфейс</span><span class="sxs-lookup"><span data-stu-id="9cb69-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
