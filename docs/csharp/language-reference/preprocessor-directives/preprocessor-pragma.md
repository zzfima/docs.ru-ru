---
title: '#pragma. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directive [C#]'
ms.assetid: 5b7944cd-d402-46a1-ad8f-feffb2d83673
ms.openlocfilehash: 3bd62364aeae0f21715711324655ef7d00d88afc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712459"
---
# <a name="pragma-c-reference"></a>#pragma (Справочник по C#)
Директива `#pragma` предоставляет компилятору специальные инструкции для компиляции файла, в котором она появляется. Компилятор должен поддерживать эти инструкции. Другими словами, директиву `#pragma` нельзя использовать для создания настраиваемых инструкций предварительной обработки. Компилятор Microsoft C# поддерживает следующие две инструкции `#pragma`:  
  
 [#pragma warning](./preprocessor-pragma-warning.md)  
  
 [#pragma checksum](./preprocessor-pragma-checksum.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
#pragma pragma-name pragma-arguments  
```  
  
## <a name="parameters"></a>Параметры  
 `pragma-name`  
 Имя распознанной директивы pragma.  
  
 `pragma-arguments`  
 Аргументы директивы pragma.  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
- [#pragma warning](./preprocessor-pragma-warning.md)
- [#pragma checksum](./preprocessor-pragma-checksum.md)
