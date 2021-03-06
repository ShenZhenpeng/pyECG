================
pyECG
================


pyECG is an opensource Python package which supports read/write of common ECG dataset formats.
Current supported formats are:

1. Physiobank `WFDB  <https://physionet.org/physiotools/wfdb.shtml>`_ (.hea/.dat)
2. `iShine  <http://thew-project.org/papers/Badilini.ISHNE.Holter.Standard.pdf>`_-formatted Holter ECG files (.ecg/.ann)


Getting Started
===================

These instructions will get you a copy of the project up and running on your local machine for development and testing 
purposes. See deployment for notes on how to deploy the project on a live system.

Prerequisites
----------------------------

To setup pyECG, you need:

1. Python 3.6
2. `ishneholterlib  <https://bitbucket.org/atpage/ishneholterlib>`_ ==2017.4.11
3. numpy==1.16.2
4. wfdb==2.2.1

Installing
----------------------------
::

 pip install pyECG


Basic Usage
----------------------------
.. code-block:: python

    from pyecg import ECGRecord

    # To load a wfdb formatted ECG record
    hea_path = "/path/to/your/hea/file"
    record = ECGRecord.from_wfdb(hea_path)

    # To load a ishine formatted ECG record
    hea_path = "/path/to/your/ecg/file"
    record = ECGRecord.from_ishine(hea_path)

    time = record.time
    signal = record.get_lead(lead_name)
    print(signal.lead_name)

License
----------------------------

Copyright 2019 Michael Tao-Yi Lee

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
