# README for all configuration files

This file contains rules how to create and where to store testline configuration files for Wroclaw SiSo team.

## JSON delta files

### file name

   There is no required schema name for delta file, but name it sensible.

### location

   Schema: `/robotws/testsuite/Wroclaw/SISO/TestLines/{testline name}/deltas/`

   Example: `/robotws/testsuite/Wroclaw/SISO/TestLines/7_16_UTE5GSISOAUTO000/deltas/`

### how to generate

1) configure BTS according to the first configuration*,
2) valid plan and download configuration as xml file, if ,
3) repeat step 1. and 2. for second configuration*,
4) go to `/robotws/testsuite/Wroclaw/SISO/CommonKeywords/RobotKeywords/` and edit  `DeltaScfGenerator.robot` file
   in the `Generate Delta` TC in method `JsonDeltaCommissioning.generate_json_delta`:

   - set full path to the first .xml file as value of `base_scf` argument,
   - set full path to the second .xml file as value of `custom_scf` argument,
   - set name of result delta file as value of `delta_file` argument (there is no required file name schema),
5) run `DeltaScfGenerator.robot`,
6) `DeltaScfGenerator.robot` save the result it's directory as {`delta_file`}.json.

   *the order of files matters! The first configuration should be base configuration of your BTS and the second - temporary. For example for some testcases.

## SCF files

### file name

Schema:

| gNB                   | eNB                |
| --------------------- | ------------------ |
| SCF_{name}_{type}.xml | SCF_{name}_LTE.xml |

|Example||

|                       gNB |                     eNB |
| ------------------------: | ----------------------: |
| SCF_SISOAUTO001_5G21A.xml | SCF_SISOAUTO001_LTE.xml |

| First Header | Second Header | Third Header |
| ------------ | :-----------: | -----------: |
| Content      |  *Long Cell*  |              |
| Content      |   **Cell**    |         Cell |

New section   |     More      |         Data |
And more      | With an escaped '\|'         ||

### file name

| One                                             | Two | Three | Four | Five | Six |
| ----------------------------------------------- | --- | ----- | ---- | ---- | --- |
| Span <td colspan=3>triple  <td colspan=2>double |     |       |      |      |     |

Accepted suffix (type) for gNB:

- `SBTS_master`,
- `master`,
- branch name (e.g. `5G21A`)

## Throughputs

### file name

   Schema: `{branch}.py`

   Examples: `5G21B.py`, `trunk.py`

### location

   Schema: `/robotws/testsuite/Wroclaw/SISO/TestLines/{testline name}/throughputs/`

   Example: `/robotws/testsuite/Wroclaw/SISO/TestLines/7_16_UTE5GSISOAUTO010/throughputs/`

### data storage

   Schema:
