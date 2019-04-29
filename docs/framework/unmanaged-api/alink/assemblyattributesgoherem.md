---
title: Класс AssemblyAttributesGoHereM (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69167fda194e9d916f44751fd1f9dcee92822377
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790147"
---
# <a name="assemblyattributesgoherem-class"></a>AssemblyAttributesGoHereM-класс

Используется ALink как заполнитель для хранения сведений о пользовательских атрибутах.

## <a name="syntax"></a>Синтаксис

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a>Примечания

Ссылки на этот тип можно включать в модули NETMODULE, источник которых содержат пользовательские атрибуты сборки. При построении манифеста сборки из одного или нескольких файлов, содержащих ссылки на эти NETMODULE, ALink использует сведения, подключенные к этим ссылкам, для выдачи фактических пользовательских атрибутов. Таким образом, экземпляр этого типа никогда не создается, а ссылки на него используются только как часть процесса сборки и бесполезны в окончательной сборке.

Ссылки на этот тип указывают пользовательские атрибуты, не связанные с безопасностью, но многократного использования.

Эти типы помечены как «внутренние» в .NET Framework и находятся в папке <xref:System.Runtime.CompilerServices> пространства имен.

## <a name="requirements"></a>Требования

mscorlib.dll

## <a name="see-also"></a>См. также

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
