---
title: Метод IMetaDataImport::FindField
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437950"
---
# <a name="imetadataimportfindfield-method"></a>Метод IMetaDataImport::FindField
Возвращает указатель на токен FieldDef для поля, заключенного в заданный <xref:System.Type> и имеющего указанное имя и подпись метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 окне Маркер TypeDef для класса или интерфейса, который заключает поле для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной.  
  
 `szName`  
 окне Имя искомого поля.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных поля.  
  
 `cbSigBlob`  
 окне Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 заполняет Указатель на соответствующий токен FieldDef.  
  
## <a name="remarks"></a>Примечания  
 Поле задается с помощью включающего класса или интерфейса (`td`), его имени (`szName`) и, при необходимости, его сигнатуры (`pvSigBlob`).  
  
 Подпись, передаваемая `FindField`, должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. (Токен является индексом локальной таблицы TypeDef). Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindField`.  
  
 `FindField` находит только поля, которые были определены непосредственно в классе или интерфейсе; наследуемые поля не находятся.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
