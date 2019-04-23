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
ms.openlocfilehash: 661c27b9c21f77104b8a86163d3c92d44f8a85df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181783"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="b2d16-102">Метод ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="b2d16-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="b2d16-103">Инициализирует средство чтения символов с интерфейсом средства импорта метаданных, что средство чтения будет сопоставлено, а также имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="b2d16-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2d16-104">Этот метод может вызываться только один раз и должен вызываться до всех остальных методов чтения.</span><span class="sxs-lookup"><span data-stu-id="b2d16-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d16-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2d16-105">Syntax</span></span>  
  
```  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2d16-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2d16-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="b2d16-107">[in] Интерфейс импорта метаданных, с которым будет связано данное средство чтения.</span><span class="sxs-lookup"><span data-stu-id="b2d16-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="b2d16-108">[in] Имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="b2d16-108">[in] The file name of the module.</span></span> <span data-ttu-id="b2d16-109">Можно использовать `pIStream` параметра вместо этого.</span><span class="sxs-lookup"><span data-stu-id="b2d16-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="b2d16-110">[in] Путь для поиска.</span><span class="sxs-lookup"><span data-stu-id="b2d16-110">[in] The path to search.</span></span> <span data-ttu-id="b2d16-111">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b2d16-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="b2d16-112">[in] Файловый поток, используемый в качестве альтернативы в параметре filename.</span><span class="sxs-lookup"><span data-stu-id="b2d16-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2d16-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2d16-113">Return Value</span></span>  
 <span data-ttu-id="b2d16-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="b2d16-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2d16-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2d16-115">Remarks</span></span>  
 <span data-ttu-id="b2d16-116">Необходимо указать только один из `filename` или `pIStream` параметров, не оба.</span><span class="sxs-lookup"><span data-stu-id="b2d16-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="b2d16-117">Параметр `searchPath` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b2d16-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2d16-118">Требования</span><span class="sxs-lookup"><span data-stu-id="b2d16-118">Requirements</span></span>  
 <span data-ttu-id="b2d16-119">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b2d16-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d16-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b2d16-120">See also</span></span>

- [<span data-ttu-id="b2d16-121">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="b2d16-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
