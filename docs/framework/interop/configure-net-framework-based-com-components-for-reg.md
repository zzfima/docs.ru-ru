---
title: Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации
ms.date: 03/30/2017
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
ms.openlocfilehash: 9e273bd3e4bf2bb6945fe48c850783a54fa9a869
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291758"
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a>Практическое руководство. Настройка COM-компонентов на основе платформы .NET Framework для активации без регистрации
Активация компонентов на основе платформы .NET Framework без регистрации осуществляется лишь немного сложнее, чем для COM-компонентов. При установке требуются два манифеста:  
  
- Для определения управляемого компонента в COM-приложениях используется манифест приложения в стиле Win32.  
  
- Компоненты на основе платформы .NET Framework используют манифест компонента для получения необходимых для активации сведений во время выполнения.  
  
 В этом разделе описывается, как связать манифест приложения с приложением, манифест компонента с компонентом и внедрить манифест компонента в сборку.  
  
## <a name="create-an-application-manifest"></a>Создание манифеста приложения  
  
1. С помощью редактора XML создайте (или измените) манифест приложения, принадлежащий COM-приложению, которое взаимодействует с одним или несколькими управляемыми компонентами.  
  
2. Вставьте следующий стандартный заголовок в начало файла:  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
    </assembly>
    ```  
  
     Дополнительные сведения об элементах манифеста и их атрибутах см. в статье [Application Manifests](/windows/desktop/SbsCs/application-manifests) (Манифесты приложений).  
  
3. Определите владельца манифеста. В следующем примере владельцем файла манифеста является `myComApp` версии 1.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="msil"
      />
    </assembly>  
    ```  
  
4. Определите зависимые сборки. В следующем примере `myComApp` зависит от `myManagedComp`.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myComApp"
                        version="1.0.0.0"
                        processorArchitecture="x86"
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"
                        name="myOrganization.myDivision.myManagedComp"
                        version="6.0.0.0"
                        processorArchitecture="X86"
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5. Сохраните файл манифеста под соответствующим именем. Имя манифеста приложения состоит из имени исполняемого файла сборки и расширения manifest. Например, для приложения myComApp.exe файл манифеста будет носить имя myComApp.exe.manifest.  
  
Манифест приложения можно установить в тот же каталог, что и COM-приложение. Также его можно добавить в качестве ресурса в EXE-файл приложения. Для получения дополнительной информации, [см.](/windows/desktop/SbsCs/about-side-by-side-assemblies-)  
  
## <a name="create-a-component-manifest"></a>Создание компонентного манифеста  
  
1. С помощью редактора XML создайте манифест компонента, описывающий управляемую сборку.  
  
2. Вставьте следующий стандартный заголовок в начало файла:  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">
    </assembly>
    ```  
  
3. Определите владельца файла. Элемент `<assemblyIdentity>` элемента `<dependentAssembly>` в файле манифеста приложения должен соответствовать аналогичному элементу в манифесте компонента. В следующем примере владельцем файла манифеста является `myManagedComp` версии 1.2.3.4.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />
    </assembly>
    ```  
  
4. Определите каждый класс в сборке. Используйте `<clrClass>` элемент для уникальной идентификации каждого класса в управляемой сборке. Атрибуты элемента, вложенного в `<assembly>`, определены в следующей таблице.  
  
    |Атрибут|Описание|Обязательно|  
    |---------------|-----------------|--------------|  
    |`clsid`|Идентификатор, который задает активируемый класс.|Да|  
    |`description`|Строка, которая сообщает пользователю о компоненте. По умолчанию используется пустая строка.|нет|  
    |`name`|Строка, представляющая управляемый класс.|Да|  
    |`progid`|Идентификатор, который используется для отложенной активации.|нет|  
    |`threadingModel`|Потоковая модель COM. По умолчанию используется значение "Both" (Оба).|нет|  
    |`runtimeVersion`|Используемая версия среды CLR. Если этот атрибут не задан, а среда CLR еще не загружена, компонент загружает последнюю установленную версию среды CLR, предшествующую версии 4. Если указать v1.0.3705, v1.1.4322 или v2.0.50727, автоматически выполняется накат версии до последней установленной версии среды CLR, предшествующей версии 4 (как правило, v2.0.50727). Если уже загружена другая версия среды CLR и не удается загрузить указанную версию в рамках параллельного процесса, загружается указанная версия. В противном случае используется загруженная версия CLR. Это может привести к сбою загрузки.|нет|  
    |`tlbid`|Идентификатор библиотеки типов, содержащей сведения о типе класса.|нет|  
  
     Во всех тегах атрибутов учитывается регистр символов. Просматривая библиотеку типов, экспортированную для сборки с помощью средства ObjectViewer OLE/COM (Oleview.exe), можно получить идентификаторы классов (CLSID), программ (ProgID), потоковые модели и версию среды выполнения.  
  
     В следующем манифесте компонента определяются два класса: `testClass1` и `testClass2`.  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5. Сохраните файл манифеста под соответствующим именем. Имя манифеста компонента состоит из имени библиотеки сборки и расширения manifest. Например, манифест для myManagedComp.dll будет носить имя myManagedComp.manifest.  
  
 Манифест компонента необходимо внедрить в сборку в качестве ресурса.  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a>Внедрение манифеста компонента в управляемую сборку  
  
1. Создайте скрипт ресурсов, содержащий следующую инструкцию:  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     В этой инструкции `myManagedComp.manifest` определяет имя внедряемого манифеста компонента. В этом примере файл скрипта будет носить имя `myresource.rc`.  
  
2. Скомпилируйте скрипт с помощью средства компиляции ресурсов Microsoft Windows (Rc.exe). В командной строке введите следующую команду:  
  
     `rc myresource.rc`  
  
     Программа Rc.exe создает файл ресурсов `myresource.res`.  
  
3. Снова скомпилируйте исходный файл сборки и укажите файл ресурсов с помощью параметра **/win32res**:  
  
    `/win32res:myresource.res`  
  
     Файл, содержащий внедренные ресурсы, также носит имя `myresource.res`.  
  
## <a name="see-also"></a>См. также

- [COM-взаимодействие без регистрации](registration-free-com-interop.md)
- [Требования для COM-взаимодействия без регистрации](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f8h7012w(v=vs.100))
- [Настройка COM-компонентов для активации без регистрации](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/x65a421a(v=vs.100))
- [Пошаговое руководство. Активация компонентов на основе платформы .NET без регистрации](https://docs.microsoft.com/previous-versions/dotnet/articles/ms973915(v=msdn.10))
