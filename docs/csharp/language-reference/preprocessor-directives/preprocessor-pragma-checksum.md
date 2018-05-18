---
title: '##pragma checksum (справочник по C#)'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 603b56325d7b690a153bd7db41f34621675a4ba6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
 Глобальный уникальный идентификатор (GUID) для хэш-алгоритма.  
  
 `"checksum_bytes"`  
 Строка шестнадцатеричных цифр, представляющая байты контрольной суммы. Должно быть четным числом шестнадцатеричных цифр. Нечетное число цифр вызовет предупреждение во время компиляции, и директива будет пропущена.  
  
## <a name="remarks"></a>Примечания  
 Отладчик Visual Studio использует контрольную сумму, чтобы подтвердить нахождение правильного источника. Компилятор вычисляет контрольную сумму для исходного файла, а затем передает результат в файл базы данных (PDB) программы. Отладчик затем использует PDB-файл для сравнения с контрольной суммой, вычисленной им для исходного файла.  
  
 Это решение не работает для проектов [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)], так как контрольная сумма вычисляется для созданного исходного файла, а не для ASPX-файла. Чтобы решить эту проблему, `#pragma checksum` обеспечивает поддержку контрольных сумм для страниц [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)].  
  
 При создании проекта [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] в Visual C# сгенерированный исходный файл содержит контрольную сумму для ASPX-файла, из которого создается источник. Затем компилятор записывает эти данные в PDB-файл.  
  
 Если компилятор не обнаруживает директиву `#pragma checksum` в файле, он вычисляет контрольную сумму и записывает значение в PDB-файл.  
  
## <a name="example"></a>Пример  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Директивы препроцессора C#](../../../csharp/language-reference/preprocessor-directives/index.md)
