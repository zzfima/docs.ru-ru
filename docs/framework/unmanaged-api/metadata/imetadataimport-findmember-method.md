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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4eefb7ec1e7d0d130ec64531a59d1d5bbce04963
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968918"
---
# <a name="imetadataimportfindmember-method"></a>Метод IMetaDataImport::FindMember
Возвращает указатель на токен мембердеф для поля или метода, заключенного в заданный объект <xref:System.Type> с указанным именем и сигнатурой метаданных.  
  
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
 окне Размер в байтах для `pvSigBlob`.  
  
 `pmb`  
 заполняет Указатель на соответствующий токен Мембердеф.  
  
## <a name="remarks"></a>Примечания  
 Элемент указывается с помощью включающего класса или интерфейса (`td`), его имени (`szName`) и (при необходимости) его сигнатуры (`pvSigBlob`). В классе или интерфейсе может быть несколько членов с одним и тем же именем. В этом случае передайте сигнатуру члена, чтобы найти уникальное совпадение.  
  
 Подпись, передаваемая `FindMember` в, должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. Токен является индексом локальной таблицы TypeDef. Нельзя построить сигнатуру времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для входных данных `FindMember`.  
  
 `FindMember`находит только элементы, которые были определены непосредственно в классе или интерфейсе; Он не находит наследуемых членов.  
  
> [!NOTE]
> `FindMember`— Это вспомогательный метод. Он вызывает метод [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Если этот вызов не находит совпадения, `FindMember` то вызывает метод [IMetaDataImport:: финдфиелд](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** COR. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
