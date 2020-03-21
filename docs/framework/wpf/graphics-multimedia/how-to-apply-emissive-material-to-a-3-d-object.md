---
title: Как применить эмиссионный материал к 3D-объекту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112158"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a>Как применить эмиссионный материал к 3D-объекту
Ниже приводится пример, <xref:System.Windows.Media.Media3D.EmissiveMaterial> как использовать для добавления цвета к существующему материалу, равному цвету кисти EmissiveMaterial. Приведенный ниже <xref:System.Windows.Media.Media3D.DiffuseMaterial> <xref:System.Windows.Media.Media3D.EmissiveMaterial> код показывает и применяется в комбинации, чтобы добавить синий цвет к внешнему виду DiffuseMaterial.  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 В процедурном кодексе:  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a>Пример  
 Следующий код показывает весь образец в XAML.  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a>Пример  
 Ниже приведен авоту всего образца в процедурном кодексе.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Создание 3D-сцены](how-to-create-a-3-d-scene.md)
- [3D Графика Обзор](3-d-graphics-overview.md)
- [Оживите свойства материала в 3D-сцене](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Применить материал к передней и задней части 3D-объекта](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
