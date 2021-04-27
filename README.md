## Awan

Monitor and manage cloud budget, resources, and organize cloud by tagging.

### Authentication

Awan::provider('aws')->withCredentials('key', 'secret') => AWS;

Awan::provider('gcp')->withCredentials('project_id', 'secret_path') => GCP;

Awan::actual();

#### Budget
Awan::budget();
Awan::forecast();

Awan::setBudget('2000');
Awan::setCurrency('$');

#### Connect to specific provider 

Awan::provider('aws')->cost('forecast');
Awan::provider('aws')->cost('actual');

Awan::provider('aws')->setBudget(1000);
Awan::provider('aws')->setCurrency('IDR');
Awan::provider('aws')->setCurrencyConversion(14500)

Awan::provider('aws')->cost('budget');

Awan::providers();
Awan::sync();

#### Resources
Awan::provider('gcp')->resources('vm')->list();
Awan::provider('aws')->resources('vm')->search();

#### Tag
Awan::provider('gcp')->resources('vm')->project('cost')->list();
Awan::provider('gcp')->resources('vm')->environment('production')->list();
Awan::provider('gcp')->resources('vm')->service('cost')->list();
Awan::provider('gcp')->resources('vm')->team('cost')->list();

