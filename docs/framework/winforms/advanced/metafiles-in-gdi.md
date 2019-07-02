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
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504586"
---
# <a name="metafiles-in-gdi"></a>Метафайлы в GDI+
GDI + предоставляет <xref:System.Drawing.Imaging.Metafile> таким образом, чтобы можно было записывать и отображать метафайлы. Метафайл, также называемый векторного изображения, — это образ, который хранится в виде последовательности команд и параметров рисования. Команды и параметры, сохраненные в <xref:System.Drawing.Imaging.Metafile> объекта можно хранить в памяти или сохранить файл или поток.  
  
## <a name="metafile-formats"></a>Метафайлы  
 GDI + позволяет отображать метафайлы, сохраненные в следующих форматах:  
  
- Метафайл Windows (WMF)  
  
- EMF (Enhanced Metafile —расширенный метафайл)  
  
- EMF +  
  
 GDI + позволяет сохранять метафайлы в форматы EMF и EMF +, но не в формате WMF.  
  
 EMF + является расширением формата EMF, кроме записей GDI + для сохранения. Существует две разновидности формат EMF +. EMF + только и EMF + Dual. Метафайлы EMF + Only содержат только записи GDI +. Такие метафайлы могут отображаться в GDI +, но не в GDI. Метафайлы EMF + Dual содержат записи GDI + и GDI. Каждая запись GDI + в метафайле EMF + Dual сопряжен с альтернативной записью GDI. Такие метафайлы могут отображаться GDI или GDI +.  
  
 В следующем примере отображается метафайл, который был ранее сохранен как файл. Метафайл отображается с его верхнего левого угла в (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>См. также

- [Изображения, точечные рисунки и метафайлы](images-bitmaps-and-metafiles.md)
