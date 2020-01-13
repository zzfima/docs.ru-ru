---
title: <remarks> — Руководство по программированию на C#
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 2391a8ee0bb55402ff5183c837e36d04a39e6555
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711705"
---
# <a name="remarks-c-programming-guide"></a>\<remarks> (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a>Параметры  
 `Description`  
 Описание элемента.  
  
## <a name="remarks"></a>Примечания  
 Тег \<remarks> позволяет добавить сведения о типе, дополняющие информацию, указанную с помощью тега [\<summary>](./summary.md). Эти сведения отображаются в окне "Обозреватель объектов".  
  
 Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Рекомендуемые теги для комментариев документации](./recommended-tags-for-documentation-comments.md)
