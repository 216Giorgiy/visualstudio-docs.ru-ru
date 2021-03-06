---
title: Программу командной строки | Документация Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: db75b3a7-80b2-4a74-91d2-fd6e0f73b45d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: be492ea3d9e61e25c28d8fc74ab870d7a6f959a5
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717563"
---
# <a name="command-line-capture-tool"></a>Программа командной строки для захвата
DXCap.exe — это программа командной строки для захвата и воспроизведения данных диагностики графики. Она поддерживает все функциональные уровни Direct3D версий 10–12.

## <a name="syntax"></a>Синтаксис

```cmd
DXCap.exe [-file filename] [-frame frames | -period periods | -manual] -c app [args...]
DXCap.exe -p [filename] [-debug | -warp | -hw] [-config] [-rawmode]
DXCap.exe -p [filename] -screenshot [-frame frames]
DXCap.exe -p [filename] -toXML [xml_filename]
DXCap.exe -v [-file filename] [-examine events] [-haltonfail | -exitonfail] [-showprogress]
DXCap.exe -e [search_string]
DXCap.exe -info
```

#### <a name="parameters"></a>Параметры
 `-file` `filename` В режиме захвата (`-c`), `filename` указывает имя, графические данные записываются в файл журнала графики. Если `filename` не задан, графические данные записываются в файл с именем `<appname>-<date>-<time>.vsglog` по умолчанию.

 В режиме проверки (-v) параметр `filename` определяет имя файла журнала графики, который необходимо проверить. Если `filename` не указан, используется журнал графики, который проверялся в последний раз.

 `-frame` `frames` В режиме захвата параметр `frames` определяет кадры, которые необходимо захватить. Первый кадр имеет номер 1. Можно указать несколько кадров, используя запятую или использовать диапазоны. Например если `frames` — `2, 5, 7-9, 15`, затем кадры `2`, `5`, `7`, `8`, `9`, и `15` регистрируются.

> [!TIP]
> Используйте `-frame` `manual` для указания, что кадры будут захватываться вручную, нажав клавишу Print Screen. Кадры можно захватывать, когда приложение запущено. Чтобы остановить захват кадров, вернитесь в интерфейс командной строки и нажмите клавишу ВВОД.

 `-period` `periods` В режиме захвата параметр `periods` определяет интервал времени (в секундах), в течение которого необходимо захватывать кадры. Можно указать несколько периодов, используя запятую или использовать диапазоны. Например если `periods` — `2.1-5, 7.0-9.3`, а затем кадры, отрисовываемые между `2.1` и `5` секунд и между`7` и `9.3` регистрируются секунд.

 `-c` `app` [`args...`] Режим захвата. В режиме захвата параметр `app` определяет имя приложения, из которого необходимо захватить графические данные. `args...` определяет дополнительные параметры командной строки для этого приложения.

 `-p` [`filename`] Режим воспроизведения (`-p`). В режиме воспроизведения параметр `filename` определяет имя файла журнала графики, который необходимо воспроизвести. Если `filename` не указан, повторно используется журнал графики, которое последнего воспроизводилось.

 `-debug` В режиме воспроизведения `-debug` указывает на то, что воспроизведение должна воспроизводиться с включенным уровнем отладки Direct3D.

 `-warp` В режиме воспроизведения `-warp` указывает на то, что воспроизведение должна воспроизводиться с помощью программной отрисовки Warp.

 `-hw` В режиме воспроизведения `-hw` указывает на то, что воспроизведение должна воспроизводиться с помощью оборудования GPU.

 `-config` В режиме воспроизведения `-config` отображаются все сведения о компьютере, который был использован для записи файла журнала графики.

 `-rawmode` В режиме воспроизведения `-rawmode` указывает то, что воспроизведение должно осуществляться без изменения записанных событий. В обычном режиме воспроизведения в воспроизводимые данные могут вноситься небольшие изменения с целью упростить отладку и ускорить воспроизведение. Например, вместо выполнения команд цепочки буферов выходные данные цепочки буферов могут имитироваться. Обычно это воспроизведения не является проблемой, но может потребоваться воспроизведения в виде, более точно записанное событие. Например этот параметр можно использовать для восстановления поведения полноэкранной отрисовке в приложении, которое было захвачено в полноэкранном режиме.

 `-toXML` [`xml_filename`] В режиме воспроизведения параметр `xml_filename` определяет имя файла, в который записывается XML-представление воспроизводимых данных. Если параметр `xml_filename` не задан, XML-представление записывается в файл, имя которого совпадает с именем воспроизводимого файла, но с расширением `.xml`.

 `-v` Режим проверки. В режиме проверки захваченные кадры воспроизводятся на оборудовании и в WARP, а результаты сравниваются с помощью функции сравнения изображений. С помощью этой возможности можно быстро выявить проблемы с драйвером, влияющие на отрисовку.

 `-examine` `events` В режиме проверки параметр `events` определяет набор событий графики, непосредственные результаты которых необходимо сравнить. Например `-examine present,draw,copy,clear` ограничивает сравниваемые только события, относящиеся к указанным категориям.

> [!TIP]
>  Мы рекомендуем начать с `-examine present,draw,copy,clear` так, как это будет выявлено большинство проблем, но значительно быстрее, чем более широкий набор событий. При необходимости вы можете указать другой набор событий для проверки, чтобы выявить другие проблемы.

 `-haltonfail` В режиме проверки `-haltonfail` останавливает проверку при обнаружении различий между оборудованием и отрисовщик WARP. Проверка возобновляется после нажатия клавиши.

 `-exitonfail` В режиме проверки `-exitonfail` выходит из проверки, сразу же при обнаружении различий между оборудованием и отрисовщик WARP. При выходе из программы таким образом, он возвращает `0` в среду; в противном случае возвращается `1`.

 `-showprogress` В режиме проверки `-showprogress` отображает сведения о ходе выполнения сеанса проверки подлинности. Ход отрисовки WARP показан слева, а ход аппаратной отрисовки — справа.

 `-e` `search_string` Перечисление установленных приложений универсальной платформы Windows. Эти сведения можно использовать для захвата командной строки с приложениями универсальной платформы Windows.

 `-info` Выводит информацию о компьютере и библиотеках DLL захвата.

## <a name="remarks"></a>Примечания
 Программа DXCap.exe работает в трех режимах.

 Режим захвата (-c) захватывать графические данные из работающего приложения и записываются в файл журнала графики. Возможности захвата и формат файла аналогичны используемым в Visual Studio.

 Режим воспроизведения (-p) воспроизведение ранее захваченных событий графики из существующего файла журнала графики. По умолчанию воспроизведение осуществляется в окне, даже если файл журнала графики был захвачен из полноэкранного приложения. Воспроизведение осуществляется в полноэкранном режиме, только если графики файл журнала был захвачен из полноэкранного приложения и `-rawmode` указан.

 Режим проверки (`-v`) проверка поведения отрисовки путем воспроизведения захваченных кадров на оборудовании и в WARP, а затем для сравнения результатов с помощью функции сравнения изображений. С помощью этой возможности можно быстро выявить проблемы с драйвером, влияющие на отрисовку.

 Помимо этих режимов, программа dxcap.exe выполняет еще две функции, которые не предусматривают захват или воспроизведение графических данных.

 Функция перечисления (`-e`) отображает сведения о приложениях универсальной платформы Windows, установленных на компьютере. Эти сведения включают в себя имя пакета и идентификатор appid, определяющий исполняемый файл в приложение универсальной платформы Windows. Для захвата графических данных из приложения Магазина Windows с помощью программы DXCap.exe используйте имя пакета и идентификатор appid вместо имени исполняемого файла, которое используется при захвате данных из классического приложения.

 Функция вывода информации (`-info)` отображаются сведения о компьютере и библиотеках DLL захвата.

## <a name="examples"></a>Примеры

### <a name="capture-graphics-information-from-a-desktop-app"></a>Захват графических данных из классического приложения
 Используйте `-c` чтобы указать приложение, из которого требуется захватывать графические данные.

```cmd
DXCap.exe -c BasicHLSL11.exe
```

 По умолчанию графические данные записываются в файл с именем `<appname>-<date>-<time>.vsglog`. Используйте `-file` чтобы указать другой файл для записи.

```cmd
DXCap.exe -file regression_test_12.vsglog -c BasicHLSL11.exe
```

 Чтобы указать дополнительные параметры командной строки для приложения, из которого захватываются данные, добавьте их после имени файла приложения.

```cmd
DXCap.exe -c "C:\Program Files\Internet Explorer\iexplorer.exe" "www.fishgl.com"
```

 Команда в приведенном выше примере захватывает графические данные из классической версии браузера Internet Explorer во время просмотра веб-страницы по адресу www.fishgl.com, которая использует API WebGL для отрисовки трехмерного содержимого.

> [!NOTE]
>  Так как аргументы командной строки, находящиеся после имени приложения, передаются в него, аргументы, предназначенные для программы DXCap.exe, необходимо указать перед параметром `-c`.

### <a name="capture-graphics-information-from-a-uwp-app"></a>Захват графических данных из приложения универсальной платформы Windows.
 Вы можете захватывать графические данные из приложения универсальной платформы Windows.

```cmd
DXCap.exe -c Microsof.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps
```

 Отслеживание из приложения UWP с помощью DXCap.exe так же, как для записи из классического приложения Windows, но вместо указания приложения по имени файла, определить приложения универсальной платформы Windows, по имени пакета и имя или идентификатор исполняемого файла внутри этого пакета требуется  захват с. Чтобы упростить узнать, как определить приложений универсальной платформы Windows, установленных на компьютере, используйте `-e` DXCap.exe с параметром для их перебора:

```cmd
DXCap.exe -e
```

 Вы можете указать дополнительную строку поиска, чтобы найти конкретное приложение. Если строка поиска, DXCap.exe перечисляет приложения универсальной платформы Windows, имя пакета, имя приложения или идентификаторы приложений соответствует строке поиска. При поиске не учитывается регистр.

```cmd
DXCap.exe -e map
```

 Приведенная выше команда перечисляет приложений универсальной платформы Windows, которые соответствуют «сопоставить»; Ниже приведен результат.

 **Пакет «Microsoft.BingMaps»:** **InstallDirectory: C:\Program Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe** **FullName: Microsoft.BingMaps_2.1.2914.1734_x64 __8wekyb3d8bbwe** **UserSID: S-1-5-21-2127521184-1604012920-1887927527-5603533** **имя: Microsoft.BingMaps** **издатель: CN = Microsoft Corporation, O = Microsoft Corporation, L = Redmond, S = Washington, C = US** **версии: 2.1.2914.1734** **можно будет запустить приложения:** **идентификатор: AppexMaps** **Exe-файла: C:\Program Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe\Map.exe** **IsWWA: нет** **AppSpec (для запуска): DXCap.exe - c Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps** в последней строке выходных данных для каждого перечисленного приложения приводится команда, можно использовать для захвата графических данных из него.

### <a name="capture-specific-frames-or-frames-between-specific-times"></a>Захват определенных кадров или кадров в течение определенного интервала
 Используйте `-frame` чтобы указать кадры, которые необходимо записать через запятую или использовать диапазоны:

```cmd
DXCap.exe -frame 2,5,7-9,15 -c SimpleBezier11.exe
```

 Также можно использовать `-period` указать диапазон времени, во время которых должны захватываться кадры. Интервалы времени указываются в секундах; можно задать несколько интервалов.

```cmd
DXCap.exe -period 2.1-5, 7.0-9.3 -c SimpleBezier11.exe
```

### <a name="capture-frames-interactively"></a>Захват кадров в интерактивном режиме
 Используйте `-manual` для захвата кадров в интерактивном режиме. Чтобы начать захват, нажмите клавишу ВВОД. Чтобы остановить захват, нажмите клавишу ВВОД еще раз.

```cmd
DXCap.exe -manual -c SimpleBezier11.exe
```

### <a name="play-back-a-graphic-log-file"></a>Воспроизведение файла журнала графики
 Используйте `-p` Чтобы воспроизвести ранее захваченный файл журнала графики.

```cmd
DXCap.exe -p regression_test_12.vsglog
```

 Чтобы воспроизвести последний захваченный журнал графики, не указывайте имя файла.

```cmd
DXCap.exe -p
```

### <a name="play-back-in-raw-mode"></a>Воспроизведение в режиме исходных данных
 Используйте `-rawmode` Чтобы воспроизвести захваченные команды в точности так, как их возникновения. В обычном режиме воспроизведения некоторые команды эмулируются. Например, файл журнала графики, захваченный из полноэкранного приложения, будет воспроизводиться в окне. При включении режима исходных данных будет предпринята попытка воспроизведения этого файла в полноэкранном режиме.

```cmd
DXCap.exe -p regression_test_12.vsglog -rawmode
```

### <a name="play-back-using-warp-or-a-hardware-device"></a>Воспроизведение с помощью WARP или аппаратного устройства
 Вам может потребоваться принудительно воспроизвести файл журнала графики, захваченный на аппаратном устройстве, с помощью WARP или принудительно воспроизвести журнал, захваченный в WARP, с помощью аппаратного устройства. Используйте `-warp` для воспроизведения с помощью WARP.

```cmd
DXCap.exe -p regression_test_12.vsglog -warp
```

 Используйте `-hw` для воспроизведения с помощью оборудования.

```cmd
DXCap.exe -p regression_test_12.vsglog -hw
```

### <a name="validate-a-graphics-log-file-against-warp"></a>Проверка файла журнала графики относительно WARP
 В режиме проверки файл журнала графики воспроизводится как на оборудовании, так и в WARP, после чего результаты сравниваются. Это может помочь определить ошибки отрисовки, вызванные драйвером. Чтобы проверить правильность работы графического оборудования в сравнении с WARP, используйте параметр -v.

```cmd
DXCap.exe -v regression_test_12.vsglog
```

 Чтобы уменьшить количество сравнений, вы можете указать подмножество команд для сравнения; остальные команды будут игнорироваться. Чтобы указать команды, результаты которых нужно сравнить, используйте параметр -examine.

```cmd
DXCap.exe -v regression_test_12.vsglog -examine present,draw,copy,clear
```

### <a name="convert-a-graphics-log-file-to-pngs"></a>Преобразование файла журнала графики в файлы PNG
 Для просмотра и анализа кадров из файла журнала графики программа DXCap.exe может сохранять захваченные кадры как файлы изображений PNG. Используйте `-screenshot` для в режиме воспроизведения захваченных кадров в виде PNG-файлы.

```cmd
DXCap.exe -p BasicHLSL11.vsglog -screenshot
```

 Используйте `-frame` с `-screenshot` чтобы указать кадры, которые нужно вывести.

```cmd
DXCap.exe -p BasicHLSL11.vsglog -screenshot -frame 5, 7-9
```

### <a name="convert-a-graphics-log-file-to-xml"></a>Преобразование файла журнала графики в XML
 Для обработки и анализа журналов графики с помощью привычных средств, таких как FindStr или XSLT, программа DXCap.exe преобразовать файл журнала графики в формат XML. Используйте `-toXML` в режиме воспроизведения для преобразования журнала в XML вместо его воспроизведения обратно.

```cmd
DXCap.exe -p regression_test_12.vsglog -toXML
```

 По умолчанию выходные данные XML записываются в файл с тем же именем, что и у файла журнала, но с расширением XML. В приведенном выше примере XML-файл будет называться **regression_test_12.xml**. Чтобы присвоить файлу XML другое имя, укажите его после `-toXML`.

```cmd
DXCap.exe -p regression_test_12.vsglog -toXML temp.xml
```

 Получившийся файл будет содержать код XML наподобие следующего:

```xml
<Moment value="67"/>
<Method name="CreateDXGIFactory1" >
    <Return type="HRESULT" value="S_OK" />
    <Parameter name="riid" type="IID" value="770AAE78-F26F-4DBA-A829-253C83D1B387" />
    <Parameter name="ppFactory" type="void" handle="1" isOutput="true" />
</Method>

<Moment value="167"/>
<Method name="D3D11CreateDevice" >
    <Return type="HRESULT" value="S_OK" />
    <Parameter name="pAdapter" type="IDXGIAdapter" handle="34" />
    <Parameter name="DriverType" type="D3D_DRIVER_TYPE" value="D3D_DRIVER_TYPE_UNKNOWN" />
    <Parameter name="Software" type="HMODULE" value="pointer" />
    <Parameter name="Flags" type="UINT" value="0" />
    <Parameter name="pFeatureLevels" type="D3D_FEATURE_LEVEL" arrSize="1" >
        <Element value="D3D_FEATURE_LEVEL_11_0" />
    </Parameter>
    <Parameter name="FeatureLevels" type="UINT" value="1" />
    <Parameter name="SDKVersion" type="UINT" value="7" />
    <Parameter name="ppDevice" type="ID3D11Device" handle="35" isOutput="true" />
    <Parameter name="pFeatureLevel" type="D3D_FEATURE_LEVEL" value="D3D_FEATURE_LEVEL_11_0" isOutput="true" />
    <Parameter name="ppImmediateContext" type="ID3D11DeviceContext" value="nullptr" isOutput="true" />
</Method>
```

## <a name="requirements"></a>Требования