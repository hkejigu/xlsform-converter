# xlsform-converter (xlsconv)

xlsform-converter converts surveys defined via the [XLSForm standard] into [Django models] and HTML5 [Mustache templates].  This makes it possible to re-use the powerful form building tools provided by the [Open Data Kit ecosystem][ecosystem], while leveraging Django's robust support for relational databases like [PostgreSQL].

xlsform-converter is designed to facilitate the rapid development of offline-capable data collection apps via the [wq framework].  The ultimate goal is to provide full compatibility with the form authoring tools provided by [ODK (and Enketo, etc.)][ecosystem].  Note that this is not the same as full XForm compatibility: the client and server components of wq ([wq.app] and [wq.db]) use a JSON-based [REST API] to exchange data and are not directly compatible with their ODK Analogues (ODK Collect and ODK Aggregate, respectively).

[![Latest PyPI Release](https://img.shields.io/pypi/v/xlsconv.svg)](https://pypi.python.org/pypi/xlsconv)
[![Release Notes](https://img.shields.io/github/release/wq/xlsform-converter.svg)](https://github.com/wq/xlsform-converter/releases)
[![License](https://img.shields.io/pypi/l/xlsconv.svg)](https://github.com/wq/xlsform-converter/blob/master/LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/wq/xlsform-converter.svg)](https://github.com/wq/xlsform-converter/stargazers)
[![GitHub Forks](https://img.shields.io/github/forks/wq/xlsform-converter.svg)](https://github.com/wq/xlsform-converter/network)
[![GitHub Issues](https://img.shields.io/github/issues/wq/xlsform-converter.svg)](https://github.com/wq/xlsform-converter/issues)

[![Travis Build Status](https://img.shields.io/travis/wq/xlsform-converter/master.svg)](https://travis-ci.org/wq/xlsform-converter)
[![Python Support](https://img.shields.io/pypi/pyversions/xlsconv.svg)](https://pypi.python.org/pypi/xlsconv)

### Usage

```bash
pip3 install xlsconv

# Use the default models.py template
xls2django my-odk-survey.xls > myapp/models.py

# Use a custom template
xls2django my-odk-survey.xls my_templates/models.py > myapp/models.py

# Use the default form.html template
xls2html my-odk-survey.xls > templates/survey_form.html

# Use a custom template
xls2html my-odk-survey.xls my_templates/form.html > templates/survey_form.html
```

If you are using wq, you may be interested in [wq.start], which uses xlsconv internally for the `wq addform` and `wq maketemplates` commands.

[XLSForm standard]: http://xlsform.org/
[Django models]: https://docs.djangoproject.com/en/1.9/topics/db/models/
[Mustache templates]: https://wq.io/docs/templates
[ecosystem]: https://enketo.org/openrosa
[PostgreSQL]: http://www.postgresql.org/
[wq framework]: https://wq.io/
[wq.app]: https://wq.io/wq.app
[wq.db]: https://wq.io/wq.db
[REST API]: https://wq.io/docs/url-structure
[wq.start]: https://github.com/wq/wq-django-template
