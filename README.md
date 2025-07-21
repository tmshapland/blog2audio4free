# blog2audio4free

Convert a blog to an audio file and play it on your iPhone without paying for any subscriptions.

I fall behind constantly on the content I want to read, especially AI-related content. I also am fairly frequently doing chores or some other task during which I could be listening to something on my Airpods. But I can't find the specific content about what I want need to read in podcasts. I want to listen to any written content I find on the internet.

The following is basically the same as Kevin Thompson's (blogpost)[https://kevinthompson.info/blog/converting-blog-posts-to-audio-files/] on converting a blog to audio. The only difference is that I spell out more of the steps. 

But wait, why not just use something like Speechify? Answer: Because I have to pay a subscription for it. 

But wait, why not use something like NotebookLM to turn the written content into a podcast? Answer: Because I want to listen to the content itself, as the author wrote it, not an LLM's re-interpretation of the content.

The workflow is as follows:
 - Copy blog content into a .txt file.
 - Use your Mac's text to speech engine to convert it to audio.
 - Airdrop the audio file to your iPhone.
 - Import the audio file into the Pocket Casts media player.

## Setup

### Setup Step 1. Set up your Mac's native text to speech. 

Your Mac has a built-in text to speech engine. The default voice is a jarring, so here are the steps to converting it to a smoother Siri voice.

  - Open `System Settings > Accessibility > Spoken Content`
  - Click the little info icon next to System Voice. This part was tricky. I couldn't find the Siri voices in the dropdown from the Spoken Content main menu. It's hidden under the info icon. (see screenshot below)
  - Click Voice. 
  - In the search bar, type Siri. Then choose a voice to your liking.

INSERT SCREENSHOT HERE

### Setup Step 2. Download Pocket Casts onto your iPhone.

You will need a media player for listening to the audio file on your phone. 

You could use the media player the iPhone opens by default when you play an audio file from your Files app, but it lacks features like resuming from where you left off and buttons for skipping backwards and forward. 

You could use the Apple Music mobile app, but you need a subscription to Apple Music to move a file from your Mac to the Music app on your iPhone. 

The (Pocket Casts)[https://apps.apple.com/us/app/pocket-casts-podcast-player/id414834813] iPhone app allows you to import files from your iPhone to the app. It has the media player features that I want. You can do this all on their free tier. (To sync from the Pocket Casts web app to the mobile app, you need a subscription.)

## Usage

### Step 1. Copy and paste the blog content

Copy the content of your blog and paste it into `input.txt`.

I recognize that I could have done something fancier here where the users inputs a URL, but this works fine. 

## Step 2. Clean up the blog post for listening

It's hard to listen to code and tables. You'll want to delete them from `input.txt`. Optionally, you can open `input.txt` in Cursor and ask Cursor to "Remove all tables and code from this text", but it'll cost you some tokens and I'm trying to do this without paying for anything. But I love the idea of using Cursor for non-coding tasks. 

## Step 3. Convert the blog post to audio using Mac's native text to speech engine.

In a terminal, type the following. Be sure to update your file paths and names. I prefer to output to my Downloads directory because it's easier to find it there for the next step (i.e., copying the file with my phone). 

```bash
say -f input.txt --progress -o ~/Downloads/2021_07_going_beyond.m4a
```

## Step 4. Airdrop the audio file to your phone.

Right click on the audio file, click share, click Airdrop, then click on your phone. 

## Step 5. Copy the file to Pocket Casts

Open the Files app on your iPhone. Find the file you uploaded. Tap and hold, then click share. Scroll through the list of apps and select Pocket Casts. (You can also do this step from within Pocket Casts).

## Step 6. Listen to the content you're falling behind on while doing dishing, commuting, et cetera. 

Open the Pocket Casts app, tap profile, tap files, select your audio file, and listen. 