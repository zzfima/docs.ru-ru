---
title: Практическое руководство. Проверка структур Point4D на равенство и неравенство
ms.date: 03/30/2017
helpviewer_keywords:
- inequality [WPF], testing Point4D structures for
- equality [WPF], testing Point4D structures for
- testing [WPF], Point4D structures for equality
- Point4D structures [WPF], testing for inequality
- testing [WPF], Point4D structures for inequality
- Point4D structures [WPF], testing for equality
ms.assetid: e004a67e-db7f-4af8-a31f-e6b2a44ccf34
ms.openlocfilehash: 1ec844c8fb0aceaaec6030c2e9d5cb30cf984f43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559818"
---
# <a name="how-to-test-point4d-structures-for-equality-and-inequality"></a>Практическое руководство. Проверка структур Point4D на равенство и неравенство
В этом примере показано, как проверить <xref:System.Windows.Media.Media3D.Point4D> структуры на равенство и неравенство.  
  
 Следующий код иллюстрирует, как проверить <xref:System.Windows.Media.Media3D.Point4D> структуры на равенство и неравенство с помощью <xref:System.Windows.Media.Media3D.Point4D> методов проверки на равенство.  <xref:System.Windows.Media.Media3D.Point4D> Структуры проверяются на равенство с помощью перегруженного равенства (`==`) оператор, затем на неравенство с помощью перегруженного оператора неравенства (`!=`) оператор и, наконец, <xref:System.Windows.Media.Media3D.Point3D> структуры и <xref:System.Windows.Media.Media3D.Point4D> Структура проверяются на равенство с помощью статического <xref:System.Windows.Media.Media3D.Point4D.Equals%2A> метод.  
  
## <a name="example"></a>Пример  
 [!code-csharp[3DGallery_procedural_snip#Point4DEqualityExample_csharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Misc3DOperationsExample.cs#point4dequalityexample_csharp)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Media3D.Point4D.op_Equality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.op_Inequality%2A>  
 <xref:System.Windows.Media.Media3D.Point4D.Equals%2A>
