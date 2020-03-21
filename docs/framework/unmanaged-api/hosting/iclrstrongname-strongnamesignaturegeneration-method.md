---
title: Метод ICLRStrongName::StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGeneration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type:
- apiref
ms.openlocfilehash: e58ac181c4e472c469076b880ff71e0c6afa30fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178042"
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>Метод ICLRStrongName::StrongNameSignatureGeneration
Создает подпись строгого имени для указанной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 (в) Путь к файлу, содержащий манифест сборки, для которого будет создана сильная подпись имени.  
  
 `wszKeyContainer`  
 (в) Название ключевого контейнера, содержащего публичную/частную ключевую пару.  
  
 Если `pbKeyBlob` он `wszKeyContainer` недействителен, необходимо указать действительный контейнер в рамках поставщика криптографических услуг (CSP). В этом случае пара ключей, хранящаяся в контейнере, используется для подписания файла.  
  
 Если `pbKeyBlob` он не является нулевым, то предполагается, что ключевая пара содержится в ключевом бинарном большом объекте (BLOB).  
  
 Ключи должны быть 1024-разрядные ривест-Шамир-Адлеман (RSA) подписания ключей. В настоящее время никакие другие типы ключей не поддерживаются.  
  
 `pbKeyBlob`  
 (в) Указатель на публичную/частную ключевую пару. Эта пара находится в формате, `CryptExportKey` созданном функцией Win32. Если `pbKeyBlob` он недействителен, `wszKeyContainer` то предполагается, что указанный ключевым контейнер омыт в паре ключа.  
  
 `cbKeyBlob`  
 (в) Размер, в байтах, из `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 (ваут) Указатель на место, к которому общее время выполнения языка возвращает подпись. Если `ppbSignatureBlob` время выполнения является нулевым, время выполнения `wszFilePath`хранит подпись в файле, указанном .  
  
 Если `ppbSignatureBlob` время выполнения общего языка не является нулевым, то время выполнения общего языка выделяет пространство для возврата подписи. Звонящее должно освободить это пространство с помощью метода [ICLRStrongName::StrongNameFreeBuffer.](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
  
 `pcbSignatureBlob`  
 (ваут) Размер, в байтах, возвращенной подписи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`если метод успешно завершен; в противном случае значение HRESULT, указывающем на сбой (см. [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  
 Укажите `wszFilePath` нулевую для расчета размера подписи без создания подписи.  
  
 Подпись может храниться либо непосредственно в файле, либо возвращена вызывающему.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MetaHost.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Интерфейс ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
