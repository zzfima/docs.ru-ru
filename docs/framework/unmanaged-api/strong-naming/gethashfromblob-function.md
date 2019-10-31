---
title: Функция GetHashFromBlob
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140712"
---
# <a name="gethashfromblob-function"></a>Функция GetHashFromBlob

Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.

Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) .

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Параметры

`pbBlob`\
окне Указатель на адрес блока памяти, который необходимо хэшировать.

`cchBlob`\
окне Длина блока памяти в байтах.

`piHashAlg`\
[вход, выход] Константа, указывающая хэш-алгоритм. Используйте нуль для алгоритма по умолчанию.

`pbHash`\
заполняет Возвращаемый буфер хэша.

`cchHash`\
окне Запрошенный максимальный размер `pbHash`.

`pchHash`\
заполняет Размер возвращаемого `pbHash`в байтах.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** StrongName. h

**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll

**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Метод GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
