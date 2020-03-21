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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177285"
---
# <a name="imetadataimportfindmember-method"></a>Метод IMetaDataImport::FindMember
Получает указатель на токен MemberDef для поля или метода, который прилагается указанным <xref:System.Type> и который имеет указанное имя и подпись метаданных.  
  
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
 (в) Токен TypeDef для класса или интерфейса, который примыкает к поиску участника. Если это `mdTokenNil`значение, то поиск выполняется для глобально-переменной или глобальной функции.  
  
 `szName`  
 (в) Имя участника для поиска.  
  
 `pvSigBlob`  
 (в) Указатель на двоичную подпись метаданных участника.  
  
 `cbSigBlob`  
 (в) Размер байтов `pvSigBlob`.  
  
 `pmb`  
 (ваут) Указатель на соответствующий токен MemberDef.  
  
## <a name="remarks"></a>Remarks  
 Вы указываете участника, используя его`td`прилагающий`szName`класс или интерфейс (), его имя (), и по желанию его подпись ().`pvSigBlob` В классе или интерфейсе может быть несколько членов с одинаковым именем. В этом случае, пройти подпись члена, чтобы найти уникальный матч.  
  
 Подпись, `FindMember` переданная, должна быть сгенерирована в текущей области, поскольку подписи привязаны к определенной области. Подпись может вставлять маркер, который определяет класс или тип значения. Токен — это индекс в локальной таблице TypeDef. Нельзя создавать подпись времени выполнения вне контекста текущей области и использовать `FindMember`эту подпись в качестве ввода для ввода.  
  
 `FindMember`находит только участников, которые были определены непосредственно в классе или интерфейсе; он не находит наследственных членов.  
  
> [!NOTE]
> `FindMember`является методом помощника. Он называет [IMetaDataИмпорт::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); если этот вызов не находит `FindMember` совпадения, то звонит [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Cor.h  
  
 **Библиотека:** Включено в качестве ресурса в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
