# READme
👋 NULLTRACE — Personal Security Lab

Cybersecurity student • CTF player • Linux enthusiast • Network tinkerer • Builder






📌 About

Hi.

I'm a first-year student slowly falling deeper into cybersecurity.

This repository started as a place for code and notes, but eventually became a dump for almost everything I work on: CTF notes, networking experiments, Linux commands, small scripts, project ideas, lab records, screenshots, competition results, random observations, and things I probably should have organized better.

If you're looking through this repository, expect a lot of noise.

That's intentional.

Some of the useful information is obvious.

Some of it is buried in old notes.

Some of it is duplicated.

Some of it is probably useless.

And a few details make more sense when you compare them with older records.

🧭 2026 — THE TIMELINE

Month

Event

Notes

January

Linux

Started seriously experimenting with Linux

February

Networking

Started learning TCP/IP, DNS, HTTP and packet capture

March

First CTF

First proper Capture The Flag competition

April

Null Trace

Started competing regularly with a small team

May

PacketSleuth

Began building a packet-analysis utility

June

First Podium

1st place with Null Trace

July

Another CTF

Returned to competition with better preparation

August

Still Learning

Continued labs, projects and CTF practice

The important thing about the timeline is that it wasn't planned.

One thing led to another.

Linux led to networking.

Networking led to packet analysis.

Packet analysis led to CTFs.

CTFs led to Null Trace.

Null Trace led to more projects.

And the projects created more questions.

🗂️ REPOSITORY MAP

A lot of this repository is deliberately messy.

/
├── README.md
├── notes/
│   ├── linux/
│   ├── networking/
│   ├── web/
│   ├── crypto/
│   ├── forensics/
│   └── random/
│
├── ctf/
│   ├── first-ctf/
│   ├── north-byte-2026/
│   ├── july-event/
│   └── writeups/
│
├── packetsleuth/
│   ├── src/
│   ├── captures/
│   ├── exports/
│   └── experiments/
│
├── scripts/
│   ├── bash/
│   ├── python/
│   └── utilities/
│
├── labs/
│   ├── linux/
│   ├── networking/
│   ├── web/
│   └── forensics/
│
├── journal/
│   ├── 2026-01.md
│   ├── 2026-02.md
│   ├── 2026-03.md
│   ├── 2026-04.md
│   ├── 2026-05.md
│   ├── 2026-06.md
│   ├── 2026-07.md
│   └── 2026-08.md
│
└── archive/
    ├── old-notes/
    ├── screenshots/
    ├── broken-scripts/
    └── TODO.md

🐧 JANUARY — LINUX

January was mostly:

install Linux
break Linux
search why Linux broke
fix Linux
break something else
repeat

The first notes are not impressive.

They're mostly basic commands.

pwd
ls
cd
mkdir
touch
cp
mv
rm
cat
less
grep
find
chmod
chown
ps
top
kill
ip
ss
curl
wget

Eventually I started paying attention to what the commands were actually doing.

First useful notes

File permissions

rwx
421

Examples:

chmod 755 script.sh
chmod 644 notes.txt
chmod +x scanner.sh

I initially thought permissions were mostly annoying.

Later they became extremely useful when working through CTF machines.

Processes

Things I wrote down:

ps aux
ps -ef
top
htop
pgrep
kill

One of the first notes I kept:

"If you don't know what a process is doing, don't randomly kill it."

Still good advice.

Networking from Linux

The first commands I started using regularly:

ip addr
ip route
ip neigh
ss -tulpn
ping
traceroute
dig
nslookup
curl -I

I started noticing that networking was not just a subject in class.

It was underneath almost everything.

🌐 FEBRUARY — NETWORKING RABBIT HOLE

February was where things became much more interesting.

The notes started getting longer.

TCP/IP notes

Things I wanted to understand:

Application
    ↓
Transport
    ↓
Internet
    ↓
Link

TCP concepts:

SYN

SYN/ACK

ACK

sequence numbers

acknowledgements

retransmissions

ports

connection states

FIN

RST

A simplified connection:

CLIENT                         SERVER

   SYN  ------------------------>

        <---------------- SYN/ACK

   ACK  ------------------------>

             CONNECTED

I kept coming back to the same question:

"What does this actually look like on the wire?"

That question eventually became the reason PacketSleuth existed.

📡 PACKET CAPTURE NOTES

Tools experimented with:

Wireshark

tcpdump

tshark

Example lab commands:

tcpdump -i eth0
tcpdump -i eth0 -nn
tcpdump -i eth0 port 53
tcpdump -i eth0 port 80
tcpdump -w capture.pcap

I learned that a packet capture can contain far more information than the application shows you directly.

Things worth checking:

source
destination
protocol
port
length
flags
timing
DNS
HTTP
TLS metadata
TCP behavior
retransmissions

🔎 DNS NOTES

Questions I wrote down:

What happens when I type a domain?
Where does DNS fit?
What is recursive resolution?
What are A records?
What are AAAA records?
What is CNAME?
What is TTL?

Useful commands:

dig example.com
dig A example.com
dig AAAA example.com
dig MX example.com
dig NS example.com

One notebook page simply said:

"DNS is basically the phone book until you start looking closer."

🌍 HTTP NOTES

HTTP became another rabbit hole.

Things I started recording:

GET
POST
PUT
PATCH
DELETE
HEAD
OPTIONS

Headers:

Host
User-Agent
Accept
Content-Type
Content-Length
Cookie
Authorization
Referer
Origin

Response codes:

200
201
204
301
302
304
400
401
403
404
405
429
500
502
503

The more I learned, the more CTF web challenges started making sense.

🏁 MARCH — FIRST CTF

My first proper CTF was a reality check.

I knew some commands.

I did not know how to turn that knowledge into a solution quickly.

The first competition notes contain things like:

recon
enumeration
don't panic
read the prompt
check source
look at headers
try obvious things first
don't overcomplicate

And, repeatedly:

WHY DID I NOT CHECK THAT FIRST?

First CTF categories

The categories I encountered included:

Web

Crypto

Forensics

Misc

OSINT

PWN

The biggest lesson was not a particular exploit.

It was methodology.

🧠 MY BASIC CTF CHECKLIST

1. Read the challenge carefully
2. Identify what is actually given
3. List assumptions
4. Enumerate before guessing
5. Check obvious files
6. Inspect metadata
7. Look for patterns
8. Automate repetitive work
9. Record observations
10. Only then try complicated approaches

🌐 WEB CTF NOTES

Things I started checking during authorized CTF challenges:

robots.txt
sitemap.xml
HTML source
JavaScript
cookies
response headers
URL parameters
forms
API endpoints
error messages

The important lesson:

Don't assume the visible webpage is the entire application.

🕵️ FORENSICS NOTES

Basic workflow:

identify file
↓
check metadata
↓
check strings
↓
inspect structure
↓
extract artifacts
↓
correlate timestamps
↓
form hypothesis
↓
verify

Useful commands:

file sample
strings sample
sha256sum sample
xxd sample

🔐 CRYPTO NOTES

The early crypto notes are full of mistakes.

I initially mixed up:

encoding
encryption
hashing
obfuscation

Eventually:

Encoding

Designed for representation.

Examples:

Base64
hex
URL encoding

Hashing

One-way transformation used for integrity, identification, password storage schemes, etc.

Encryption

Designed to protect confidentiality using a key.

That distinction fixed several embarrassing CTF mistakes.

👥 APRIL — NULL TRACE

By April, CTFs stopped being a solo activity.

Four people started working together.

NULL TRACE

Different approaches. Same goal.

The team wasn't built around everyone knowing everything.

It worked because different people noticed different things.

🧑‍💻 TEAM

Member

Main strengths

Secondary interests

Alex Thomas

Web security, recon

Scripting

Arjun Nair

Networking, forensics

OSINT

Dev Menon

Linux, PWN

Binary analysis

Rohan Mathew

Cryptography, scripting

Web

Team workflow

When a challenge appeared:

                CHALLENGE
                    |
          +---------+---------+
          |         |         |
        RECON     ANALYSIS   THEORY
          |         |         |
          +---------+---------+
                    |
                 TESTING
                    |
                  FLAG

The best thing about the team was that nobody had to pretend they understood something immediately.

Someone would say:

"I don't know what this is."

Someone else:

"Wait, I have seen this before."

And suddenly the problem became smaller.

🏆 JUNE — NORTH BYTE CTF 2026

Result

🥇 1ST PLACE

Team: Null Trace

Event: North Byte CTF 2026

The scoreboard became one of the most important screenshots in the repository.

Final team result:

1. Null Trace
2. segfault
3. byte bandits
4. 0x4rk
5. symlink
6. café404
7. picoCTFers
8. try_harder

🏆 NORTH BYTE — TEAM RECORD

TEAM
Null Trace

PLACEMENT
1st

STATUS
Completed

STRATEGY
parallelize challenges

PRIMARY AREAS
web
forensics
networking
crypto
misc

📋 SELECTED COMPETITION NOTES

Web

General workflow:

inspect
enumerate
understand request
understand response
identify assumptions
test within challenge scope
document result

The important lesson:

A web challenge often rewards understanding the application more than throwing tools at it.

Forensics

We found that small details mattered:

timestamps
file names
metadata
strings
embedded content
archives
logs

One note from the competition:

"Don't discard boring files."

That line stayed in the notes.

Networking

Packet captures were particularly interesting.

Questions we asked:

Who talked to whom?
When?
Using what protocol?
Which host initiated the conversation?
Was there unusual DNS?
Were there retransmissions?
What happened immediately before the suspicious event?

🛠️ MAY — PACKETSLEUTH

PacketSleuth started as a small experiment.

The idea:

Make packet analysis easier to understand while learning how packets actually work.

PacketSleuth

Concept

capture
   ↓
parse
   ↓
classify
   ↓
filter
   ↓
analyze
   ↓
visualize
   ↓
export

Intended features

Packet capture import

Protocol identification

Filtering

Basic statistics

Conversation grouping

Export

Search

Timeline view

Simple anomaly indicators

Example output

PacketSleuth
------------

Capture: capture.pcapng

Packets captured:   14532
Packets processed:  14532

Protocols:
TCP                  8120
UDP                  3910
DNS                   820
HTTP                  410
TLS                  1272

Duration: 00:02:15

Status:
[####################] COMPLETE

📦 PROJECT NOTES

The first version was ugly.

Very ugly.

The interface looked like something built at 2 AM because it was.

But the architecture gradually became clearer.

Input
  |
  +--> PCAP
  |
  +--> PCAPNG
  |
  +--> live capture
          |
          v
     packet parser
          |
          v
     protocol layer
          |
          v
       analyzer
       /   |   \
      /    |    \
   stats  filter  export

🧪 PACKETSLEUTH EXPERIMENT LOG

Experiment 01 — TCP handshake

Goal:

Understand a complete TCP connection.

Observation:

SYN
SYN/ACK
ACK

Result:

Success.

Experiment 02 — DNS

Goal:

Observe DNS traffic.

Questions:

What gets queried?
Which resolver is used?
What response arrives?
How does TTL appear?

Result:

Much easier to understand after seeing actual packets.

Experiment 03 — HTTP

Goal:

Inspect a simple HTTP request in a controlled lab.

Look for:

method
host
path
headers
response
status
content type

Result:

HTTP suddenly felt much less abstract.

Experiment 04 — Filtering

Goal:

Reduce thousands of packets to something meaningful.

Concept:

all packets
    ↓
protocol filter
    ↓
host filter
    ↓
port filter
    ↓
time window

Result:

Analysis became much faster.

🧰 TOOLS I KEEP COMING BACK TO

Linux
Wireshark
tcpdump
tshark
Python
Bash
Git
curl
dig
ss
grep
awk
sed
find
strings
file
xxd

Not because they are magical.

Because understanding basic tools makes complicated tools easier to understand.

🐍 PYTHON NOTES

Python became my main language for small security utilities.

Typical things I automate:

file processing
log parsing
packet statistics
CSV generation
text filtering
small CTF helpers
repetitive calculations

Example learning pattern:

for item in items:
    if interesting(item):
        results.append(item)

Simple code is often enough.

💻 BASH NOTES

A few commands I use constantly:

grep
cut
sort
uniq
head
tail
awk
sed
xargs

One of the most useful combinations:

cat file.txt | sort | uniq -c | sort -nr

The actual lesson wasn't the command.

It was learning to chain small tools together.

🔬 LAB RECORDS

This section contains some of the boring stuff.

It is here because boring records sometimes become useful later.

LAB — NETWORK INTERFACES

Commands:

ip addr
ip link
ip route

Things recorded:

interface names
MAC addresses
IPv4 addresses
IPv6 addresses
default route
DNS configuration

No real credentials or private information are stored here.

LAB — LISTENING SERVICES

Command:

ss -tulpn

Questions:

Which services are listening?
Which ports are open?
Which process owns the socket?
Is the service expected?

LAB — DNS LOOKUP

Commands:

dig example.com
dig +short example.com
dig MX example.com
dig NS example.com

Notes:

A       IPv4 address
AAAA    IPv6 address
CNAME   canonical name
MX      mail exchange
NS      name server
TXT     text record

📝 JOURNAL EXCERPTS

The journal is where most of the unstructured material lives.

2026-01

Installed Linux again.

Broke something.

Fixed it.

Learned that reading error messages is faster than randomly changing commands.

2026-02

Networking is much bigger than I thought.

Every time I understand one layer, there are three more things underneath it.

2026-03

First CTF.

I knew enough to recognize some things but not enough to solve quickly.

Need better methodology.

2026-04

Null Trace started becoming a real team.

Four people looking at the same problem is surprisingly useful.

2026-05

PacketSleuth finally started looking like an actual project instead of a pile of experiments.

Still ugly.

Still useful.

2026-06

We won.

I keep opening the scoreboard screenshot just to make sure it actually says 1.

2026-07

Another CTF.

Much less panic this time.

Still too much coffee.

2026-08

Still learning.

There is always something else to understand.

📊 PERSONAL LEARNING RECORD

Linux

██████████████░░░░░░ 70%

Comfortable with:

shell navigation

permissions

processes

networking commands

package management

scripting basics

logs

filesystem investigation

Still learning:

kernel concepts

advanced debugging

system internals

deeper performance analysis

Networking

████████████░░░░░░░░ 60%

Comfortable with:

TCP/IP basics

DNS

HTTP

ports

sockets

packet captures

Still learning:

routing deeply

advanced TCP behavior

wireless networking

network architecture

Web Security

██████████░░░░░░░░░░ 50%

Learning:

request/response behavior

authentication concepts

session handling

input validation

common web challenge patterns

APIs

Forensics

█████████░░░░░░░░░░░ 45%

Learning:

metadata

file analysis

packet analysis

log analysis

artifact correlation

Cryptography

███████░░░░░░░░░░░░░ 35%

Current focus:

encoding
hashing
symmetric encryption
public-key concepts
number theory basics
CTF-style puzzles

🧩 RANDOM NOTES

This repository contains a lot of these.

Note #001

If something looks weird, don't immediately assume it's complicated.

Note #002

Check the obvious things first.

Note #003

Read the error message.

Note #004

Keep notes while solving.

Note #005

If you solved it but can't explain why, you didn't really learn it yet.

Note #006

Automate boring things.

Note #007

Don't run tools blindly.

Note #008

Understand the output.

Note #009

Sleep occasionally.

Note #010

Coffee is not a debugging strategy.

🗃️ OLD PROJECT IDEAS

Some never happened.

Some might.

[ ] DNS visualizer
[ ] HTTP header analyzer
[ ] PCAP timeline viewer
[ ] simple log correlation tool
[ ] CTF note organizer
[ ] lightweight port/service inventory tool
[ ] packet conversation visualizer
[ ] forensic artifact collector
[ ] terminal-based study tracker
[ ] better PacketSleuth UI

🧪 BROKEN EXPERIMENTS

There are plenty.

old_scanner.py

Status:

BROKEN

Problem:

bad argument handling

Lesson:

Validate inputs before writing 300 lines of logic.

packet_parser_v1.py

Status:

ARCHIVED

Problem:

assumed packet structure

Replacement:

packet_parser_v2.py

ctf_notes_old.md

Status:

MESS

Contents:

TODO
try this
maybe
????
check source
why
ask team
later

Kept for historical reasons.

📅 COMPETITION HISTORY

Date

Event

Team

Result

March 2026

First CTF

Solo / practice group

Learning experience

May 2026

North Byte CTF 2026

Null Trace

1st Place

July 2026

Another CTF

Null Trace

Participated

🏆 NULL TRACE — NORTH BYTE CTF RECORD

Team

A.Thomas
A.Nair
D.Menon
R.Mathew

Roles

A.
    Web / Recon

A.
    Networking / Forensics

D.
    Linux / PWN

R.
    Crypto / Scripting

Team rule

Different approaches. Same goal.

📸 MEDIA / EVIDENCE INDEX

Some files in the repository correspond to milestones.

media/
├── first-ctf.jpg
├── null-trace.jpg
├── packetsleuth.jpg
├── north-byte-scoreboard.png
├── north-byte-certificate.png
├── late-night-lab.jpg
└── timeline-2026.jpg

The screenshots aren't all equally useful.

Some are just memories.

Some contain technical notes.

Some show project progress.

Some were uploaded because I liked the photo.

🧠 HOW I APPROACH A NEW PROBLEM

When something breaks:

observe
  ↓
describe
  ↓
reproduce
  ↓
isolate
  ↓
test
  ↓
understand
  ↓
fix
  ↓
document

The order matters.

🔍 SECURITY MINDSET

I'm trying to move away from:

"Which command should I run?"

toward:

"What am I actually trying to determine?"

For example:

Instead of:

run scanner

Think:

What assets exist?
What services are exposed?
What behavior is unexpected?
What evidence supports the conclusion?

That change has probably helped more than memorizing another hundred commands.

📚 CURRENT STUDY LIST

Linux internals
TCP/IP
DNS
HTTP
Web application architecture
Authentication
Session management
Packet analysis
Digital forensics
Python scripting
Bash
Git
CTF methodology

🎯 GOALS

Short term

Complete more CTFs

Improve Linux fluency

Understand networking properly

Improve Python

Finish PacketSleuth

Write better notes

Medium term

Build useful security tools

Contribute to open source

Become stronger at web security

Learn reverse engineering

Improve forensic analysis

Long term

Understand systems well enough that unfamiliar problems stop looking completely unfamiliar.

☕ DAILY STATUS

Sometimes the repository says:

learning

Sometimes:

debugging

Sometimes:

why

Sometimes:

it works
DO NOT TOUCH IT

And occasionally:

sleep

📈 PROGRESS

The biggest change from January to August wasn't the number of tools I learned.

It was the way I approached problems.

January:

"What command fixes this?"

August:

"What is actually happening?"

That difference matters.

🧾 CHANGELOG

v0.1 — January

Linux experiments

Basic shell notes

First scripts

v0.2 — February

Networking notes

TCP/IP experiments

DNS research

Packet captures

v0.3 — March

First CTF

Initial writeups

Challenge methodology

v0.4 — April

Null Trace formed

Team workflow established

v0.5 — May

PacketSleuth started

PCAP analysis experiments

v1.0 — June

North Byte CTF 2026

1st Place

First major team win

v1.1 — July

Another CTF

Improved preparation

More structured notes

v1.2 — August

Continued learning

PacketSleuth improvements

More Linux/networking practice

🗑️ THINGS THAT SHOULD PROBABLY BE CLEANED UP

This list has existed for longer than it should.

TODO:
- clean old scripts
- rename random files
- organize screenshots
- remove duplicate notes
- document PacketSleuth properly
- finish old Python utilities
- update CTF writeups
- fix spelling mistakes
- clean README

The README is obviously not clean yet.

🧩 A FEW THINGS I LEARNED THE HARD WAY

1. Enumeration beats guessing.

If you don't know what exists, you're guessing.

2. Logs are evidence.

Don't ignore them because they're boring.

3. Packet captures tell stories.

A capture isn't just a list of packets.

It's a timeline.

4. Documentation matters.

If you can't reproduce your own result tomorrow, today's solution isn't very useful.

5. Teamwork multiplies perspective.

Four people don't necessarily solve four times faster.

But four people can notice four different things.

🛡️ ETHICS

Everything in this repository is intended for:

learning

authorized labs

CTF competitions

personal projects

controlled environments

The goal is to understand systems and improve defensive/security knowledge.

Learn responsibly. Test only where you have permission.

🕰️ THE LONG VERSION OF THE TIMELINE

JAN
│
├── Linux
├── Shell
├── Permissions
├── Processes
└── "Why did I break this?"
        │
        ▼
FEB
│
├── TCP/IP
├── DNS
├── HTTP
├── Wireshark
└── Packet capture
        │
        ▼
MAR
│
├── First CTF
├── Web
├── Forensics
├── Crypto
└── "Need a better methodology"
        │
        ▼
APR
│
├── Null Trace
├── Team workflow
├── Shared notes
└── More CTF practice
        │
        ▼
MAY
│
├── PacketSleuth
├── PCAP analysis
├── Protocol parsing
└── Lots of ugly code
        │
        ▼
JUN
│
├── North Byte CTF 2026
├── Null Trace
├── Final scoreboard
└── 🥇 1ST PLACE
        │
        ▼
JUL
│
├── Another CTF
├── Better preparation
├── More notes
└── Less panic
        │
        ▼
AUG
│
├── Still learning
├── More labs
├── More networking
├── PacketSleuth
└── More questions

🔐 FINAL NOTE

If you've reached this part of the README, you have probably seen enough random information to realize that this repository is less of a polished portfolio and more of a record of the journey.

There are projects.

There are failures.

There are competition notes.

There are technical experiments.

There are old ideas.

There are photographs.

There are screenshots.

There are half-finished scripts.

There are notes written at completely unreasonable hours.

And there is a timeline connecting most of it.

The first CTF wasn't the important part.

The first project wasn't the important part.

Even the first win wasn't really the important part.

The important part was starting.

$ whoami

student

$ cat mindset.txt

learn
break
understand
repeat

$ echo $status

still_learning

$ echo $next

keep_going

One packet at a time.

