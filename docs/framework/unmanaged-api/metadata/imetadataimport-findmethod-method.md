---
title: Метод IMetaDataImport::FindMethod
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4225794740b7786c6f758c9a0953d323c31a1081
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782488"
---
# <a name="imetadataimportfindmethod-method"></a>Метод IMetaDataImport::FindMethod
Возвращает указатель на MethodDef токен для метода, который заключен заданным <xref:System.Type> , с указанной сигнатурой имени и метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 [in] `mdTypeDef` Маркер типа (класса или интерфейса), ограничивающий элемент для поиска. Если это значение равно `mdTokenNil`, а затем поиск выполняется для глобальной функции.  
  
 `szName`  
 [in] Имя метода для поиска.  
  
 `pvSigBlob`  
 [in] Указатель на двоичную подпись метаданных метода.  
  
 `cbSigBlob`  
 [in] Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 [out] Указатель на соответствующий токен MethodDef.  
  
## <a name="remarks"></a>Примечания  
 Укажите метод, с помощью его во включающий класс или интерфейс (`td`), его имя (`szName`) и при необходимости его подпись (`pvSigBlob`). Может существовать несколько методов с одинаковыми именами в классе или интерфейсе. В этом случае следует передайте сигнатуры метода, чтобы найти уникальное соответствие.  
  
 Подпись передается `FindMethod` необходимо создавать в текущей области, поскольку подписи привязаны к определенной области. Подписи можно внедрить токен, который определяет включающего класса или типа значения. Маркер — это индекс в локальной таблице TypeDef. Не удается построить выполнения вне контекста текущей области и использовать ее как входных данных, вводимых в `FindMethod`.  
  
 `FindMethod` находит только те методы, которые были определены непосредственно в классе или интерфейсе; унаследованные методы не найден.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.MethodInfo>
- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
