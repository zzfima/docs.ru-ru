---
title: Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 4495ff3c5d55779e9db113a2a59361b643841382
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251378"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления
В этом разделе показано, как использовать средство [генератора EDM (EdmGen. exe)](edm-generator-edmgen-exe.md) для проверки файлов модели и сопоставления. Дополнительные сведения см. в разделе [EDM](../entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Проверка модели School при помощи программы EdmGen.exe  
  
1. Создайте базу данных School. Дополнительные сведения см. [в разделе Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Сформируйте модель School. Дополнительные сведения см. в разделе [Практическое руководство. Используйте EdmGen. exe для создания файлов](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)модели и сопоставления.  
  
3. Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Настройка проекта Entity Framework вручную](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Средства EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Практическое руководство. Предварительное создание представлений для повышения производительности запросов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Практическое руководство. Использование программы EdmGen. exe для создания кода уровня объектов](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
