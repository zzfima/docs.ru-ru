---
title: Метафайлы в GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: 73cacb7f701768b42121c31cfbc4f26905961231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="metafiles-in-gdi"></a>Метафайлы в GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет <xref:System.Drawing.Imaging.Metafile> класса, можно записывать и отображать метафайлы. Метафайл, также называемый векторным рисунком, — это изображение, сохраненное в виде последовательности команд и параметров рисования. Команды и параметры, сохраненные в <xref:System.Drawing.Imaging.Metafile> объекта можно хранить в памяти или сохранить файл или поток.  
  
## <a name="metafile-formats"></a>Форматы метафайлов  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] позволяет отображать метафайлы, сохраненные в следующих форматах:  
  
-   Метафайл Windows (WMF)  
  
-   EMF (Enhanced Metafile —расширенный метафайл)  
  
-   EMF +  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] позволяет сохранять метафайлы в форматах EMF и EMF +, но не в формате WMF.  
  
 EMF + является расширением формата EMF, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] записи для сохранения. Существуют две разновидности на формат EMF +: EMF + только и EMF + Dual. Метафайлы EMF + Only содержат только [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] записей. Такие метафайлы могут отображаться с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] , но не по [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. Метафайлы EMF + Dual содержат [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] записей. Каждый [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] записей в двух EMF + метафайла, вместе с альтернативной [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] записи. Такие метафайлы могут отображаться с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] или [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 В следующем примере отображается метафайла, который был ранее сохранен в файл. Метафайл отображается с его верхнего левого угла в (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
