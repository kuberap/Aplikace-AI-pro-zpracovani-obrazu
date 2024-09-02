# Instalace a ovládání základních modelů

Budeme používat technologii docker - více viz https://docs.docker.com/get-started/docker-overview/

Naklonujeme si projekt, toto provádíme jen jednou:

'git clone --recursive --depth=1 https://github.com/dusty-nv/jetson-inference'

Přepneme do adresáře:

'cd jetson-inference/'

Spustíme docker:

'docker/run.sh'

Popis práce s dockery naleznete zde https://docs.docker.com/get-started/introduction/
My budeme používat pouze vytvořené kontejnery.

Abz se nám propsal adresář *Projects* do dockeru, budeme je spouštět následovně.
'docker/run.sh --volume $HOME/Projects:/Projects'

Výpis imagíí:

'sudo docker images'

Smazání image, můžeme potřebovat, když si budeme hrát s jazykovým modlem:

'sudo docker rmi IDIMAGE'
