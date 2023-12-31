# Senior

## Питання

### Linux

- Що може створювати високе навантаження на CPU (процеси застосунків споживають дуже мало ресурсів CPU)?
- У нас немає команд ifconfig, ip, і поставити ми їх не можемо. Як нам дізнатися ip address, mask, network, routes?
- Що таке suid, sgid та sticky?
- Що тюнилося з системою для навантаження трафіку 1GB, 10G, 40G+?
- Що тюнилося з системою для високого навантаження на диск?
- Що таке Linux namespaces?
- Що таке Ceph, як працює?
- Що потрібно тюнити для Ceph?
- Що станеться, якщо `/dev/sda1` перенесемо в `/root`?
- Ми видалили `/dev/sda1`. Як нам його відновити? Що таке pseudo-devices?
- Нам хакнули сервер, і в директорії `/var/www` створили два мільйони файлів невеликого розміру. Якщо використовувати команду cd `/var/www` і потім ``, то у нас зависне термінал. Як видалити файли?
- На якому рівні працює iptables?
- Що таке eBPF та навіщо потрібен?
- У вас є файл, який містить IP-адреси серверів (по одному в рядку). Є SSH-доступ до цих машин, і вам потрібно виконати завдання (наприклад, встановити список пакетів на всі вузли). Поясніть, як це можна зробити.

### Networking

- У чому відмінності між IPv4 та IPv6? Навіщо ми мігруємо на IPv6?
- Співіснування IPv4 та IPv6: що це означає?
- Чи справді працюють міжмережеві екрани з підтримкою IPv6?
- Як працює DHCPv6? Чим він відрізняється від DHCPv4?
- Як фрагментуються пакети IPv6 і чим це відрізняється від IPv4?
- Чи з IPv6 треба більше використовувати NAT?
- Що таке DPDK?
- Що таке SR-IOV? У чому різниця між DPDK та SR-IOV?
- Що таке NetFlow та навіщо потрібен?
- Що таке OpenFlow?
- Що таке SDN і які контролери ви знаєте? Порівняйте контролери.

### Різне

- Що таке SDLC?
- Розкажіть про останній досвід реалізації архітектури для сервісу.
- Який найважчий скрипт писали?
- Що таке configuration drift? Чому це відбувається і як це ускладнює життя інженерам\SRE\Ops?
- Розкажіть про архітектуру, за яку ви наразі відповідаєте, і вкажіть, як вона масштабована та відмовостійка.
- Назвіть три важливі KPI для DevOps-фахівця.
- Як працює Kafka (clusters(brokers, controllers), topics, partitions)?
- GitOps: Rancher Fleet vs Flux vs Argo?
- Як використовувати GitOps для оновлення документації DevOps-застосунків?
- Розкажіть про особливості проєктування Kubernetes on-premise.
- Як організувати On-call процес для команди DevOps?
- Опишіть основні кроки завантаження операційної системи Linux.

### Container orchestration

- Service mesh. Що це таке та для чого потрібно?
- Cluster federation. Що це таке та для чого потрібно?
- Pod fine-grained access. Як реалізувати? IRSA vs kube2iam vs kiam?
- Як реалізовані послуги в кубернетах?
- Як дебажити трафік контейнера?
- Що таке unikernel і навіщо він потрібний?
- Чому ком’юніті переїжджає з Docker containerd?

### Clouds and Automation

- Які переваги і недоліки cloud-провайдерів?
- Cost optimization. Які є інструменти? Spot/preemptible instances, reservations?
- Як організувати multi-account, multi-region cloud setup?
- У чому полягає різниця між приватними та публічними мережами в AWS?
- AWS Lambda: чи мали досвід роботи?
- Коли варто переходити на AWS Lambda? Коли не варто? Аналогічні рішення в GCP чи Kubernetes?
- Коли краще використовувати CloudFormation, а коли Terraform?

### CI/CD

- Що таке state в контексті використання Terraform?
- Які існують branching strategy? На що опиратись при виборі?
- Яким чином реалізувати feature/dynamic environments?
- Як зробити емуляцію ресурсів cloud-провайдера для локального тестування та прискорення розробки?
- Що таке MultiCloud?
- Що таке Cloud-Agnostic і коли він буде потрібний?
- Що таке Hybrid-Cloud та з якими рішеннями ви працювали?

### Information Security

- Як мають зберігатися паролі в базах даних (Salt&Pepper, Rainbow Tables, Adaptive Hashing)?
- Як передавати секрети в application (Secrets management)?
- Порівняйте CI/CD SAST та DAST?
- Які ви знаєте Kubernetes security practices? RBAC? OPA? Які недоліки RBAC та які кейси знаєте?
- Розкажіть про захист від DDOS атак, WAF.
- Що таке Rootless containers і навіщо він потрібний?
- Що таке AppArmor та Seccomp і навіщо вони потрібні?
- Чи доводилося працювати з Falco? Якщо так, то що реалізовували?
- HashiCorp Vault і як правильно передати нам секрети в контейнер і CI pipeline?
- Що таке Admission Controllers та які ви використовували?
- Як зберігаються секрети etcd? Як переглянути ресурси в etcd?
- Чим перевіряєте на вразливості ваш Kubernetes cluster?
- Що таке Secure SDLC?
- Що ви знаєте про Cloud Infrastructure Attack via a Pull Request і як цього уникнути?

### Observability

- Що таке observability та чим відрізняється від звичайного моніторингу? Які особливості необхідно враховувати у мікросервісній архітектурі (tracing)?
- Що таке SLI, SLO, SLA та для чого вони потрібні? Навіщо використовують error budget?

### Databases

- Що таке теорема CAP? Навіщо це треба?
- Як працювати з міграціями? Що робити у випадку rollback? Як перевірити, що міграція backward-compatible?
- Опишіть, як би ви оптимізовували роботу бази данних? (БД за вибором кандидата) Slow queries, buffers, thread pools?
- Навіщо потрібно тестувати перформанс бази даних та якими інструментами?

### Практичні завдання

- Уявіть, що ви CTO Booking чи Airbnb. Які б ви ухвалювали рішення щодо:

- Мови програмування.
- Infrastructure as a Code.
- Архітектури інфраструктури.
- Налаштування CI/CD.

- У вас є файл, який містить патчі в директорії. Наприклад:

`/var/tmp/temp/file1.c`
`/var/tmp/file.ext`
`/var/tmp/temp/`

etc... один шлях у рядку. Якщо шлях закінчується на ’/’ , це шлях до каталогу. Вам потрібно відновити це дерево каталогів із порожніми файлами в іншій файловій системі. Напишіть bash-скрипт.

- Уявіть, що вам треба переконати Spotify, що використовує AWS, перейти на GCP. Як ви мотивуєте Spotify мігрувати на GCP?
- Є сервісна компанія, яка надає сервіс трекінгу перевезень. Є клієнти, які не хочуть, щоб їхні дані процесувалися в AWS. Як нам реалізувати multi-cloud solution?
