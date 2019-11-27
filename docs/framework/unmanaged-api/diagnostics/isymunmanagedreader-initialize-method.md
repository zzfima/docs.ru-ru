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
ms.openlocfilehash: ca34d1d84d6f9960d021c35566f8412df321464d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429747"
---
# <a name="isymunmanagedreaderinitialize-method"></a><span data-ttu-id="3d0d7-102">Метод ISymUnmanagedReader::Initialize</span><span class="sxs-lookup"><span data-stu-id="3d0d7-102">ISymUnmanagedReader::Initialize Method</span></span>
<span data-ttu-id="3d0d7-103">Инициализирует средство чтения символов с помощью интерфейса средства импорта метаданных, с которым будет связан этот модуль чтения, вместе с именем файла модуля.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-103">Initializes the symbol reader with the metadata importer interface that this reader will be associated with, along with the file name of the module.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d0d7-104">Этот метод может быть вызван только один раз и должен вызываться до любых других методов чтения.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-104">This method can be called only once, and must be called before any other reader methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d0d7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d0d7-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d0d7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d0d7-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="3d0d7-107">окне Интерфейс средства импорта метаданных, с которым будет связан этот модуль чтения.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-107">[in] The metadata importer interface with which this reader will be associated.</span></span>  
  
 `filename`  
 <span data-ttu-id="3d0d7-108">окне Имя файла модуля.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-108">[in] The file name of the module.</span></span> <span data-ttu-id="3d0d7-109">Вместо этого можно использовать параметр `pIStream`.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-109">You can use the `pIStream` parameter instead.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="3d0d7-110">окне Путь для поиска.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-110">[in] The path to search.</span></span> <span data-ttu-id="3d0d7-111">Этот параметр является необязательным.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-111">This parameter is optional.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="3d0d7-112">окне Файловый поток, используемый в качестве альтернативы параметру filename.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-112">[in] The file stream, used as an alternative to the filename parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d0d7-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d0d7-113">Return Value</span></span>  
 <span data-ttu-id="3d0d7-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d0d7-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d0d7-115">Remarks</span></span>  
 <span data-ttu-id="3d0d7-116">Необходимо указать только один из параметров `filename` или `pIStream`, но не оба.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-116">You need to specify only one of the `filename` or the `pIStream` parameters, not both.</span></span> <span data-ttu-id="3d0d7-117">Параметр `searchPath` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="3d0d7-117">The `searchPath` parameter is optional.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d0d7-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3d0d7-118">Requirements</span></span>  
 <span data-ttu-id="3d0d7-119">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="3d0d7-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d0d7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="3d0d7-120">See also</span></span>

- [<span data-ttu-id="3d0d7-121">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="3d0d7-121">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
