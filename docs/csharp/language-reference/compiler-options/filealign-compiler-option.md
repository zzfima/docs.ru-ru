---
title: "-filealign (параметры компилятора C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /filealign
dev_langs:
- CSharp
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 83569fa264ba3ed6e271281885940a70a5354840
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="filealign-c-compiler-options"></a>/filealign (параметры компилятора C#)
Параметр **/filealign** позволяет указать размер разделов в выходном файле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>Аргументы  
 `number`  
 Значение, которое задает размер разделов в выходном файле. Допустимые значения: 512, 1024, 2048, 4096 и 8192. Эти значения указаны в байтах.  
  
## <a name="remarks"></a>Примечания  
 Каждый раздел выравнивается по границе, кратной значению **/filealign**. Фиксированный размер по умолчанию не предусмотрен. Если значение **/filealign** не указано, среда CLR выбирает значение по умолчанию во время компиляции.  
  
 Указанный размер раздела влияет на размер выходного файла. Изменение размера раздела может применяться для программ, выполняющихся на небольших устройствах.  
  
 Используйте [DUMPBIN](https://docs.microsoft.com/cpp/build/reference/dumpbin-options) для просмотра информации о разделах выходного файла.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте страницу **Свойства** проекта.  
  
2.  Щелкните страницу свойств **Сборка**.  
  
3.  Нажмите кнопку **Дополнительно** .  
  
4.  Измените свойство **Выравнивание файла**.  
  
 Сведения об установке этого параметра компилятора программными средствами см. в статье <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB. Практическое руководство. Изменение свойств проекта и параметров конфигурации](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
