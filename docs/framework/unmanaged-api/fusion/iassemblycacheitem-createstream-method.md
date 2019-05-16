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
ms.openlocfilehash: a98273307003485202d8c12d5c27fda04ff5a0ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629880"
---
# <a name="iassemblycacheitemcreatestream-method"></a>Метод IAssemblyCacheItem::CreateStream

Создает поток с указанным именем и формат.

## <a name="syntax"></a>Синтаксис

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

## <a name="parameters"></a>Параметры

`dwFlags`\
[in] Флаги, определенные в Fusion.idl.

`pszStreamName`\
[in] Имя потока, который должен быть создан.

`dwFormat`\
[in] Формат файла для потоковой передачи.

`dwFormatFlags`\
[in] Флаги определенного формата, определенного в Fusion.idl.

`ppIStream`\
[out] Указатель на адрес возвращаемого [IStream](/windows/desktop/api/objidl/nn-objidl-istream) экземпляра.

`puliMaxSize`\
[in, optional] Максимальный размер потока, который ссылается `ppIStream`.

## <a name="requirements"></a>Требования

**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).

**Заголовок.** Fusion.h

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyCacheItem](iassemblycacheitem-interface.md)
