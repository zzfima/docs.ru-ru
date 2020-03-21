---
title: Функция StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176933"
---
# <a name="strongnamegetpublickey-function"></a>Функция StrongNameGetPublicKey
Получает открытый ключ из пары закрытого и открытого ключей. Ключевая пара может поставляться либо в качестве ключевого имени контейнера в рамках криптографического поставщика услуг (CSP), либо в виде сырой коллекции байтов.  
  
 Эта функция была амортизирована. Вместо этого используйте метод [ICLRStrongName::StrongNameGetPublicKey.](../hosting/iclrstrongname-strongnamegetpublickey-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szKeyContainer`  
 (в) Название ключевого контейнера, содержащего публичную/частную ключевую пару. Если `pbKeyBlob` он `szKeyContainer` недействителен, необходимо указать действительный контейнер в рамках CSP. В этом `StrongNameGetPublicKey` случае извлекает открытый ключ из пары ключей, хранящейся в контейнере.  
  
 Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).  
  
 Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей. В настоящее время никакие другие типы ключей не поддерживаются.  
  
 `pbKeyBlob`  
 (в) Указатель на публичную/частную ключевую пару. Эта пара находится в формате, `CryptExportKey` созданном функцией Win32. Если `pbKeyBlob` он недействителен, `szKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.  
  
 `cbKeyBlob`  
 (в) Размер, в байтах, из `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 (ваут) Вернулся общественный ключ BLOB. Параметр `ppbPublicKeyBlob` выделяется общим временем выполнения языка и возвращается вызывающему. Звонящее должно освободить память с помощью функции [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)  
  
 `pcbPublicKeyBlob`  
 (ваут) Размер возвращенного публичного ключа BLOB.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`при успешном завершении; в `false`противном случае, .  
  
## <a name="remarks"></a>Remarks  
 Открытый ключ содержится в структуре [PublicKeyBlob.](publickeyblob-structure.md)  
  
 Если `StrongNameGetPublicKey` функция не выполняется успешно, позвоните в функцию [StrongNameErrorInfo,](strongnameerrorinfo-function.md) чтобы получить последнюю сгенерированную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Метод StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
- [Структура PublicKeyBlob](publickeyblob-structure.md)
