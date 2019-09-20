---
title: Функция StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c000aad12000a9c76fb6dd805a9b002c021be6ef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798841"
---
# <a name="strongnametokenfromassemblyex-function"></a>Функция StrongNameTokenFromAssemblyEx
Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ, который представляет маркер.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к переносимому исполняемому файлу (PE) для сборки.  
  
 `ppbStrongNameToken`  
 заполняет Возвращенный маркер строгого имени.  
  
 `pcbStrongNameToken`  
 заполняет Размер (в байтах) маркера строгого имени.  
  
 `ppbPublicKeyBlob`  
 заполняет Возвращаемый открытый ключ.  
  
 `pcbPublicKeyBlob`  
 заполняет Размер открытого ключа в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`При успешном завершении; в противном случае —. `false`  
  
## <a name="remarks"></a>Примечания  
 Маркер строгого имени — это сокращенная форма открытого ключа. Маркер представляет собой 64-разрядный хэш, созданный из открытого ключа, используемого для подписания сборки. Токен является частью строгого имени сборки и может быть считан из метаданных сборки.  
  
 После извлечения ключа и создания маркера следует вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.  
  
 Если функция `StrongNameTokenFromAssemblyEx` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** StrongName. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку Mscoree. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [Метод StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
