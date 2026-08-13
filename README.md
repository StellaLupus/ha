# ha

Личные Home Assistant blueprints и связанные конфиги/скрипты.

## Blueprints

### `blueprints/automation/stellalupus/ac_climate_control.yaml`

Климат-контроль кондиционера: выбирает режим (cool/dry/fan_only) по внешнему
датчику температуры/влажности и корректирует уставку под реальную
температуру в помещении. Учитывает защиту компрессора (минимальный интервал
между сменами режима) и устойчив к недоступности датчика влажности.

Выделен как blueprint из двух дублирующихся автоматизаций
(`Кондиционер гостиная: климат-контроль` и `Кондиционер спальня: климат-контроль`)
в основном HA — логика идентична, отличались только entity_id.

**Импорт в Home Assistant:**

Settings → Automations & Scenes → Blueprints → Import Blueprint →

```
https://github.com/StellaLupus/ha/blob/main/blueprints/automation/stellalupus/ac_climate_control.yaml
```

или через MCP-инструмент `ha_import_blueprint`.

**Обновление после правок в этом репозитории:** заново открыть тот же URL
через «Re-import blueprint» — `source_url` в файле уже на него указывает.
