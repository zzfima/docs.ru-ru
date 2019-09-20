---
title: Функция StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f062f47790136e8cd39c6751b7c75eef660c2b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799134"
---
# <a name="strongnamekeygen-function"></a>Функция StrongNameKeyGen
Создает пару открытого и закрытого ключей для использования строгого имени.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
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
  
 `ppbKeyBlob`  
 заполняет Возвращаемая пара открытого и закрытого ключей.  
  
 `pcbKeyBlob`  
 заполняет Размер (в байтах `ppbKeyBlob`).  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае —. `false`  
  
## <a name="remarks"></a>Примечания  
 `StrongNameKeyGen` Функция создает 1024-разрядный ключ. После извлечения ключа необходимо вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.  
  
 Если функция `StrongNameKeyGen` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [Метод StrongNameKeyGenEx](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
