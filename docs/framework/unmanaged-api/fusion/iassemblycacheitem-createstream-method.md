---
title: Метод IAssemblyCacheItem::CreateStream
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af7dc4e1694b66fc4a5ce37e515c71e9fa3db49
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796740"
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="4f5d9-102">Метод IAssemblyCacheItem::CreateStream</span><span class="sxs-lookup"><span data-stu-id="4f5d9-102">IAssemblyCacheItem::CreateStream Method</span></span>

<span data-ttu-id="4f5d9-103">Создает поток с указанными именем и форматом.</span><span class="sxs-lookup"><span data-stu-id="4f5d9-103">Creates a stream with the specified name and format.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f5d9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f5d9-104">Syntax</span></span>

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a><span data-ttu-id="4f5d9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f5d9-105">Parameters</span></span>

`dwFlags`\
<span data-ttu-id="4f5d9-106">окне Флаги, определенные в Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="4f5d9-106">[in] Flags defined in Fusion.idl.</span></span>

`pszStreamName`\
<span data-ttu-id="4f5d9-107">окне Имя создаваемого потока.</span><span class="sxs-lookup"><span data-stu-id="4f5d9-107">[in] The name of the stream to be created.</span></span>

`dwFormat`\
<span data-ttu-id="4f5d9-108">окне Формат файла для потоковой передачи.</span><span class="sxs-lookup"><span data-stu-id="4f5d9-108">[in] The format of the file to be streamed.</span></span>

`dwFormatFlags`\
<span data-ttu-id="4f5d9-109">окне Флаги формата, определенные в Fusion. idl.</span><span class="sxs-lookup"><span data-stu-id="4f5d9-109">[in] Format-specific flags defined in Fusion.idl.</span></span>

`ppIStream`\
<span data-ttu-id="4f5d9-110">заполняет Указатель на адрес возвращенного экземпляра [IStream](/windows/desktop/api/objidl/nn-objidl-istream) .</span><span class="sxs-lookup"><span data-stu-id="4f5d9-110">[out] A pointer to the address of the returned [IStream](/windows/desktop/api/objidl/nn-objidl-istream) instance.</span></span>

`puliMaxSize`\
<span data-ttu-id="4f5d9-111">[входные, необязательные] Максимальный размер потока, `ppIStream`на который ссылается.</span><span class="sxs-lookup"><span data-stu-id="4f5d9-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>

## <a name="requirements"></a><span data-ttu-id="4f5d9-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4f5d9-112">Requirements</span></span>

<span data-ttu-id="4f5d9-113">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f5d9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="4f5d9-114">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4f5d9-114">**Header:** Fusion.h</span></span>

<span data-ttu-id="4f5d9-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f5d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4f5d9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4f5d9-116">See also</span></span>

- [<span data-ttu-id="4f5d9-117">Интерфейс IAssemblyCacheItem</span><span class="sxs-lookup"><span data-stu-id="4f5d9-117">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
