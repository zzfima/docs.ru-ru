---
title: Функция StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176907"
---
# <a name="strongnamesignaturegeneration-function"></a>Функция StrongNameSignatureGeneration
Создает подпись строгого имени для указанной сборки.  
  
 Эта функция была амортизирована. Вместо этого используйте метод [ICLRStrongName::StrongNameSignatureGeneration.](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
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
  
 Если `ppbSignatureBlob` время выполнения общего языка не является нулевым, то время выполнения общего языка выделяет пространство для возврата подписи. Абонент должен освободить это пространство, используя функцию [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)  
  
 `pcbSignatureBlob`  
 (ваут) Размер, в байтах, возвращенной подписи.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`при успешном завершении; в `false`противном случае, .  
  
## <a name="remarks"></a>Remarks  
 Укажите `wszFilePath` нулевую для расчета размера подписи без создания подписи.  
  
 Подпись может храниться либо непосредственно в файле, либо возвращена вызывающему.  
  
 Если `StrongNameSignatureGeneration` функция не выполняется успешно, позвоните в функцию [StrongNameErrorInfo,](strongnameerrorinfo-function.md) чтобы получить последнюю сгенерированную ошибку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Метод StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
