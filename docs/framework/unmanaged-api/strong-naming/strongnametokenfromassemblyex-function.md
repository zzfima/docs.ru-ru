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
ms.openlocfilehash: 8b7866b92be3195b0a767a823a0d7fb1c0aa4918
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104246"
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
 `true` при успешном завершении; в противном случае `false`.  
  
## <a name="remarks"></a>Заметки  
 Маркер строгого имени — это сокращенная форма открытого ключа. Маркер представляет собой 64-разрядный хэш, созданный из открытого ключа, используемого для подписания сборки. Токен является частью строгого имени сборки и может быть считан из метаданных сборки.  
  
 После извлечения ключа и создания маркера следует вызвать функцию [StrongNameFreeBuffer](strongnamefreebuffer-function.md) , чтобы освободить выделенную память.  
  
 Если функция `StrongNameTokenFromAssemblyEx` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку Mscoree. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [Метод StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
