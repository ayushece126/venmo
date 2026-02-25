# Shell Programming Assignment Report

## Question 1
**Write a script to check if a specific process is running and display its PID.**

### Code (`q1.sh`)
```bash
#!/bin/bash
if [ -z "$1" ]; then
    echo "Usage: $0 <process_name>"
    exit 1
fi

PROCESS_NAME=$1
PID=$(pgrep -x "$PROCESS_NAME" || pgrep "$PROCESS_NAME")

if [ -n "$PID" ]; then
    echo "Process '$PROCESS_NAME' is running."
    echo "PID(s):"
    echo "$PID"
else
    echo "Process '$PROCESS_NAME' is not running."
fi
```

### Test Output
```text
Process 'bash' is not running.
```

## Question 2
**Create a script to display the disk usage of the home directory in a human-readable format.**

### Code (`q2.sh`)
```bash
#!/bin/bash
echo "Disk usage of Home Directory ($HOME):"
du -sh "$HOME"
```

### Test Output
```text
Disk usage of Home Directory (/Users/ayushmehta):
du: /Users/ayushmehta/Music/Music: Operation not permitted
du: /Users/ayushmehta/Music/GarageBand: Operation not permitted
du: /Users/ayushmehta/Pictures/Photo Booth Library: Operation not permitted
du: /Users/ayushmehta/Pictures/Photos Library.photoslibrary: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/CallHistoryTransactions: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/CloudDocs: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/com.apple.sharedfilelist: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/Knowledge: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/com.apple.TCC: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/FileProvider: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/AddressBook: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/FaceTime: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/DifferentialPrivacy: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/com.apple.avfoundation/Frecents: Operation not permitted
du: /Users/ayushmehta/Library/Application Support/CallHistoryDB: Operation not permitted
du: /Users/ayushmehta/Library/Assistant/SiriVocabulary: Operation not permitted
du: /Users/ayushmehta/Library/Daemon Containers: Operation not permitted
du: /Users/ayushmehta/Library/Autosave Information: Operation not permitted
du: /Users/ayushmehta/Library/IdentityServices: Operation not permitted
du: /Users/ayushmehta/Library/Calendars: Operation not permitted
du: /Users/ayushmehta/Library/Messages: Operation not permitted
du: /Users/ayushmehta/Library/HomeKit: Operation not permitted
du: /Users/ayushmehta/Library/Sharing: Operation not permitted
du: /Users/ayushmehta/Library/com.apple.aiml.instrumentation: Operation not permitted
du: /Users/ayushmehta/Library/Mail: Operation not permitted
du: /Users/ayushmehta/Library/Trial: Operation not permitted
du: /Users/ayushmehta/Library/AppleMediaServices: Operation not permitted
du: /Users/ayushmehta/Library/DuetExpertCenter: Operation not permitted
du: /Users/ayushmehta/Library/Accounts: Operation not permitted
du: /Users/ayushmehta/Library/Safari: Operation not permitted
du: /Users/ayushmehta/Library/Biome: Operation not permitted
du: /Users/ayushmehta/Library/IntelligencePlatform: Operation not permitted
du: /Users/ayushmehta/Library/Shortcuts: Operation not permitted
du: /Users/ayushmehta/Library/Suggestions: Operation not permitted
du: /Users/ayushmehta/Library/Weather: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.stocks-news: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.photolibraryd.private: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.feedback: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.siri.inference: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.telephonyutilities.callservicesd: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.swtransparency: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.coreservices.useractivityd: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.ArchiveUtility.PKSignedContainer: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.accessibility.voicebanking: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.icloud.searchpartyuseragent: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.siri.referenceResolution: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.stocks: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.usernoted: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.VoiceMemos.shared: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.contacts: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.secure-control-center-preferences: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.chronod: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/com.apple.MailPersonaStorage: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.private.translation: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.appstoreagent: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.portrait.BackgroundReplacement: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.icloud.fmfcore: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.liveactivitiesd: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.amsondevicestoraged: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.SiriTTS: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.notes.import: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.calendar: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.ip.redirects: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.siri.userfeedbacklearning: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.gamecenter: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.tips: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.tv.sharedcontainer: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.loginwindow.persistent-apps: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.spotlight: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.studentd: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.ManagedSettings: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.sharingd: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.printtool: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.corerepair: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.news: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.mobileslideshow.PhotosFileProvider: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.scopedbookmarkagent: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.weather: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/com.apple.systempreferences.cache: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.feedbacklogger: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.controlcenter: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.siri.remembers: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.notes: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/com.apple.stickersd.group: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.screencapture: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.UserNotifications: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.tipsnext: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.moments: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.Safari.SandboxBroker: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.transparency: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.reminders: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.VoiceOver: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.findmy.findmylocateagent: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.mail: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/com.apple.bird: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.DeviceActivity: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.replayd: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.Journal: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/com.apple.Home.group: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.iCloudDrive: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.FaceTime: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.energykit: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/com.apple.PreviewLegacySignaturesConversion: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.notesdebug: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.replicatord: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.Photos.PhotosFileProvider: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.icloud.fmipcore: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.AppleSpell: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.mlhost: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.FamilyControls: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.Maps: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.PegasusConfiguration: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/group.com.apple.shortcuts: Operation not permitted
du: /Users/ayushmehta/Library/Group Containers/com.apple.MessagesLegacyTransferArchive: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.VoiceMemos: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.archiveutility: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.Maps/Data/Maps: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.Home: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.Safari: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.CloudDocs.MobileDocumentsFileProvider: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.mail: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.MobileSMS: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.Notes: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.corerecents.recentsd/Data/Library/Recents: Operation not permitted
du: /Users/ayushmehta/Library/Containers/com.apple.stocks: Operation not permitted
du: /Users/ayushmehta/Library/ContainerManager: Operation not permitted
du: /Users/ayushmehta/Library/PersonalizationPortrait: Operation not permitted
du: /Users/ayushmehta/Library/Photos: Operation not permitted
du: /Users/ayushmehta/Library/Metadata/CoreSpotlight: Operation not permitted
du: /Users/ayushmehta/Library/Metadata/com.apple.IntelligentSuggestions: Operation not permitted
du: /Users/ayushmehta/Library/Reminders: Operation not permitted
du: /Users/ayushmehta/Library/Cookies: Operation not permitted
du: /Users/ayushmehta/Library/CoreFollowUp: Operation not permitted
du: /Users/ayushmehta/Library/StatusKit: Operation not permitted
du: /Users/ayushmehta/Library/DoNotDisturb: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.Music: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.HomeKit: Operation not permitted
du: /Users/ayushmehta/Library/Caches/CloudKit: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.Safari: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.findmy.fmfcore: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.containermanagerd: Operation not permitted
du: /Users/ayushmehta/Library/Caches/FamilyCircle: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.homed: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.TV: Operation not permitted
du: /Users/ayushmehta/Library/Caches/com.apple.ap.adprivacyd: Operation not permitted
du: /Users/ayushmehta/Movies/TV: Operation not permitted
du: /Users/ayushmehta/.Trash: Operation not permitted
du: /Users/ayushmehta/Documents: Operation not permitted
135G	/Users/ayushmehta
```

## Question 3
**Write a script to generate the Fibonacci sequence up to n terms, where n is provided by the user.**

### Code (`q3.sh`)
```bash
#!/bin/bash
if [ -z "$1" ]; then
    echo "Usage: $0 <n_terms>"
    exit 1
fi

N=$1

if ! [[ "$N" =~ ^[0-9]+$ ]] || [ "$N" -lt 1 ]; then
    echo "Please provide a valid positive integer."
    exit 1
fi

a=0
b=1

echo -n "Fibonacci sequence up to $N terms: "

for (( i=0; i<N; i++ ))
do
    echo -n "$a "
    fn=$((a + b))
    a=$b
    b=$fn
done
echo
```

### Test Output
```text
Fibonacci sequence up to 10 terms: 0 1 1 2 3 5 8 13 21 34
```

## Question 4
**Write a script to search for a string in a file and replace it with another string.**

### Code (`q4.sh`)
```bash
#!/bin/bash
if [ "$#" -ne 3 ]; then
    echo "Usage: $0 <file> <search_string> <replace_string>"
    exit 1
fi

FILE=$1
SEARCH=$2
REPLACE=$3

if [ ! -f "$FILE" ]; then
    echo "File '$FILE' not found!"
    exit 1
fi

# Use sed to replace the string. Mac OS sed requires an empty extension argument for in-place edit without backup.
sed -i '' "s/$SEARCH/$REPLACE/g" "$FILE"
echo "Replaced occurrences of '$SEARCH' with '$REPLACE' in '$FILE'."
```

### Test Output
```text
Replaced occurrences of 'apple' with 'orange' in 'test_dir/q4_test_copy.txt'.

File content after replacement:
Hello world. This is a orange.
```

## Question 5
**Create a script that checks whether a given string or number is a palindrome.**

### Code (`q5.sh`)
```bash
#!/bin/bash
if [ -z "$1" ]; then
    echo "Usage: $0 <string_or_number>"
    exit 1
fi

INPUT=$1
# Remove spaces and convert to lowercase for better palindrome checking (optional, but robust)
CLEAN_INPUT=$(echo "$INPUT" | tr -d ' ' | tr '[:upper:]' '[:lower:]')
REVERSE=$(echo "$CLEAN_INPUT" | rev)

if [ "$CLEAN_INPUT" == "$REVERSE" ]; then
    echo "'$INPUT' is a palindrome."
else
    echo "'$INPUT' is not a palindrome."
fi
```

### Test Output
```text
'radar' is a palindrome.

Another test:
'hello' is not a palindrome.
```

## Question 6
**Write a script that monitors a file for changes and displays a message when it is modified.**

### Code (`q6.sh`)
```bash
#!/bin/bash
if [ -z "$1" ]; then
    echo "Usage: $0 <file_to_monitor>"
    exit 1
fi

FILE=$1

if [ ! -f "$FILE" ]; then
    echo "File '$FILE' does not exist."
    exit 1
fi

echo "Monitoring '$FILE' for changes. Press [Ctrl+C] to stop."

# Get initial modification time
# On macOS, stat -f "%m" gives modification time in seconds since epoch
LTIME=$(stat -f "%m" "$FILE")

# For the assignment, we might not want it to run forever, so we'll check it once after a sleep
# Or we can just loop a few times. Let's do a loop that runs 5 times so it can be tested easily.
for i in {1..5}; do
    sleep 1
    ATIME=$(stat -f "%m" "$FILE")

    if [[ "$ATIME" != "$LTIME" ]]; then
        echo "Message: The file '$FILE' has been modified!"
        LTIME=$ATIME
    fi
done
echo "Finished monitoring '$FILE' for 5 seconds."
```

### Test Output
```text
Monitoring 'test_dir/q6_test.txt' for changes. Press [Ctrl+C] to stop.
Message: The file 'test_dir/q6_test.txt' has been modified!
Finished monitoring 'test_dir/q6_test.txt' for 5 seconds.
```

## Question 7
**Create a script to read numbers from a file, sort them in ascending order, and save the output to another file.**

### Code (`q7.sh`)
```bash
#!/bin/bash
if [ "$#" -ne 2 ]; then
    echo "Usage: $0 <input_file> <output_file>"
    exit 1
fi

INPUT_FILE=$1
OUTPUT_FILE=$2

if [ ! -f "$INPUT_FILE" ]; then
    echo "Input file '$INPUT_FILE' not found!"
    exit 1
fi

# Sort numerically (-n)
sort -n "$INPUT_FILE" > "$OUTPUT_FILE"

echo "Numbers from '$INPUT_FILE' sorted and saved to '$OUTPUT_FILE'."
cat "$OUTPUT_FILE"
```

### Test Output
```text
Numbers from 'test_dir/q7_input.txt' sorted and saved to 'test_dir/q7_output.txt'.
-5
0
1
7
19
34
42
88
```

## Question 8
**Write a script to count the number of files with specific extensions (e.g., .txt, .sh) in a directory.**

### Code (`q8.sh`)
```bash
#!/bin/bash
if [ "$#" -ne 2 ]; then
    echo "Usage: $0 <directory> <extension (e.g., .txt)>"
    exit 1
fi

DIR=$1
EXT=$2

if [ ! -d "$DIR" ]; then
    echo "Directory '$DIR' not found!"
    exit 1
fi

# Using find to accurately count files
COUNT=$(find "$DIR" -maxdepth 1 -type f -name "*$EXT" | wc -l | tr -d ' ')

echo "Number of '$EXT' files in '$DIR': $COUNT"
```

### Test Output
```text
Number of '.txt' files in 'test_dir': 7
```

## Question 9
**Write a script to display system information such as OS version, kernel version, and system uptime.**

### Code (`q9.sh`)
```bash
#!/bin/bash
echo "--- System Information ---"

# OS Version
echo "OS Version:"
sw_vers

echo ""
# Kernel Version
echo "Kernel Version:"
uname -v

echo ""
# System Uptime
echo "System Uptime:"
uptime
```

### Test Output
```text
--- System Information ---
OS Version:
ProductName:		macOS
ProductVersion:		26.2
BuildVersion:		25C56

Kernel Version:
Darwin Kernel Version 25.2.0: Tue Nov 18 21:09:55 PST 2025; root:xnu-12377.61.12~1/RELEASE_ARM64_T8103

System Uptime:
23:46  up  9:53, 2 users, load averages: 4.69 3.51 3.31
```

## Question 10
**Create a script that generates and displays the multiplication table for a given number.**

### Code (`q10.sh`)
```bash
#!/bin/bash
if [ -z "$1" ]; then
    echo "Usage: $0 <number>"
    exit 1
fi

NUM=$1

if ! [[ "$NUM" =~ ^-?[0-9]+$ ]]; then
    echo "Please provide a valid integer."
    exit 1
fi

echo "Multiplication Table for $NUM:"
for i in {1..10}
do
    RES=$((NUM * i))
    echo "$NUM x $i = $RES"
done
```

### Test Output
```text
Multiplication Table for 7:
7 x 1 = 7
7 x 2 = 14
7 x 3 = 21
7 x 4 = 28
7 x 5 = 35
7 x 6 = 42
7 x 7 = 49
7 x 8 = 56
7 x 9 = 63
7 x 10 = 70
```

