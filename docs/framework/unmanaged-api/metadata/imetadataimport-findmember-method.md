---
title: Метод IMetaDataImport::FindMember
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: 7a46fa5319a1badc0cf28dcdbf535a6ed017c9c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437918"
---
# <a name="imetadataimportfindmember-method"></a>Метод IMetaDataImport::FindMember
Возвращает указатель на токен Мембердеф для поля или метода, заключенного в заданное <xref:System.Type> и имеющего указанное имя и подпись метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 окне Токен TypeDef для класса или интерфейса, который заключает элемент для поиска. Если это значение равно `mdTokenNil`, поиск выполняется для глобальной переменной или глобальной функции.  
  
 `szName`  
 окне Имя искомого элемента.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных элемента.  
  
 `cbSigBlob`  
 окне Размер в байтах `pvSigBlob`.  
  
 `pmb`  
 заполняет Указатель на соответствующий токен Мембердеф.  
  
## <a name="remarks"></a>Примечания  
 Элемент указывается с помощью включающего класса или интерфейса (`td`), его имени (`szName`) и, при необходимости, его сигнатуры (`pvSigBlob`). В классе или интерфейсе может быть несколько членов с одним и тем же именем. В этом случае передайте сигнатуру члена, чтобы найти уникальное совпадение.  
  
 Подпись, передаваемая `FindMember`, должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. Токен является индексом локальной таблицы TypeDef. Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindMember`.  
  
 `FindMember` находит только элементы, которые были определены непосредственно в классе или интерфейсе; Он не находит наследуемых членов.  
  
> [!NOTE]
> `FindMember` является вспомогательным методом. Он вызывает метод [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Если этот вызов не находит совпадения, `FindMember` вызывает метод [IMetaDataImport:: финдфиелд](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
