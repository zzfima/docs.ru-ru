---
title: Функция StrongNameKeyGenEx
ms.date: 03/30/2017
api_name:
- StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGenEx
helpviewer_keywords:
- StrongNameKeyGenEx function [.NET Framework strong naming]
ms.assetid: 36bd10b9-9857-45f3-8d3b-0da091d6169e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9ab908866402bd7a883114466f32921321a5ee6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799015"
---
# <a name="strongnamekeygenex-function"></a>Функция StrongNameKeyGenEx
Создает новую пару открытого и закрытого ключей с указанным размером ключа для использования строгого имени.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszKeyContainer`  
 окне Запрошенное имя контейнера ключей. `wszKeyContainer`должен быть непустой строкой или иметь значение NULL для создания временного имени.  
  
 `dwFlags`  
 окне Указывает, следует ли оставить зарегистрированный ключ. Поддерживаются следующие значения:  
  
- 0x00000000 — используется, `wszKeyContainer` если параметр имеет значение null, чтобы создать имя контейнера временного ключа.  
  
- 0x00000001 (`SN_LEAVE_KEY`) — указывает, что ключ должен оставаться зарегистрированным.  
  
 `dwKeySize`  
 окне Запрошенный размер ключа в битах.  
  
 `ppbKeyBlob`  
 заполняет Возвращаемая пара открытого и закрытого ключей.  
  
 `pcbKeyBlob`  
 заполняет Размер (в байтах `ppbKeyBlob`).  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае —. `false`  
  
## <a name="remarks"></a>Примечания  
 Для подписывания сборки строгим именем в `dwKeySize` .NET Framework версиях 1,0 и 1,1 требуется a из 1024 бит. в версии 2,0 добавлена поддержка для 2048-разрядных ключей.  
  
 После извлечения ключа необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.  
  
 Если функция `StrongNameKeyGenEx` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [Метод StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
