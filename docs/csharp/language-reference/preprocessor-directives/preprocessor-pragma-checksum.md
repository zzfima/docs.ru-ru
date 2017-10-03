---
title: "#<a name=\"pragma-checksum-c-reference\"></a>#pragma checksum (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma checksum'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c48d99843b9ba398dfe8dc3cf0d2264aaf72be9f
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="pragma-checksum-c-reference"></a>#pragma checksum (Справочник по C#)
Создание контрольных сумм для исходных файлов для помощи в отладке страниц [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a>Параметры  
 `"filename"`  
 Имя файла, который требует отслеживания изменений или обновлений.  
  
 `"{guid}"`  
 Глобальный уникальный идентификатор (GUID) для файла.  
  
 `"checksum_bytes"`  
 Строка шестнадцатеричных цифр, представляющая байты контрольной суммы. Должно быть четным числом шестнадцатеричных цифр. Нечетное число цифр приведет к выводу предупреждения во время компиляции, и директива будет пропущена.  
  
## <a name="remarks"></a>Примечания  
 Отладчик Visual Studio использует контрольную сумму, чтобы подтвердить нахождение правильного источника. Компилятор вычисляет контрольную сумму для исходного файла, а затем передает результат в файл базы данных (PDB) программы. Отладчик затем использует PDB-файл для сравнения с контрольной суммой, вычисленной им для исходного файла.  
  
 Это решение не работает для проектов [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)], так как контрольная сумма вычисляется для созданного исходного файла, а не для ASPX-файла. Чтобы решить эту проблему, `#pragma checksum` обеспечивает поддержку контрольных сумм для страниц [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 При создании проекта [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] в [!INCLUDE[csprcs](~/includes/csprcs-md.md)] созданный исходный файл содержит контрольную сумму для ASPX-файла, из которого создается источник. Затем компилятор записывает эти данные в PDB-файл.  
  
 Если компилятор не обнаруживает директиву `#pragma checksum` в файле, он вычисляет контрольную сумму и записывает значение в PDB-файл.  
  
## <a name="example"></a>Пример  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)

