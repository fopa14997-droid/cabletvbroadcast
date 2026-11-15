const defaultSchedule = [
  { start: "00:00", end: "04:00", label: "Overnight archive" },
  { start: "04:00", end: "08:00", label: "Early-morning nostalgia" },
  { start: "08:00", end: "12:00", label: "Daytime classics" },
  { start: "12:00", end: "16:00", label: "Afternoon lineup" },
  { start: "16:00", end: "20:00", label: "Prime-time block" },
  { start: "20:00", end: "00:00", label: "Late-night wrap" }
];

const channelSeed = [
  { name: "A&E", networkId: "A&E", years: "1984–2026", category: "General", blurb: "Documentary, true crime, and lifestyle archive references.", query: "A&E TV archive" },
  { name: "ABC Family", networkId: "ABCF", years: "1990–2026", category: "Family", blurb: "Tween, sitcom, and family-night programming archives.", query: "ABC Family TV archive" },
  { name: "AMC", networkId: "AMC", years: "1984–2026", category: "Movies", blurb: "Movie marathons and classic-film reruns.", query: "AMC TV archive" },
  { name: "Animal Planet", networkId: "AP", years: "1996–2026", category: "Nature", blurb: "Wildlife documentaries and field reporting.", query: "Animal Planet TV archive" },
  { name: "Aspire", networkId: "ASPIRE", years: "2005–2026", category: "Lifestyle", blurb: "African American lifestyle and cultural programming.", query: "Aspire TV archive" },
  { name: "BBC America", networkId: "BBCA", years: "1998–2026", category: "British", blurb: "International drama, comedy, and travel blocks.", query: "BBC America TV archive" },
  { name: "BET", networkId: "BET", years: "1980–2026", category: "Black culture", blurb: "Music, entertainment, and community programming.", query: "BET TV archive" },
  { name: "Bravo", networkId: "BRAVO", years: "1980–2026", category: "Lifestyle", blurb: "Reality, design, and lifestyle scheduling.", query: "Bravo TV archive" },
  { name: "C-SPAN", networkId: "CSPAN", years: "1979–2026", category: "Public affairs", blurb: "Congressional and civic programming blocks.", query: "C-SPAN TV archive" },
  { name: "C-SPAN 2", networkId: "CSPAN2", years: "1986–2026", category: "Public affairs", blurb: "Book talks, hearings, and public debate.", query: "C-SPAN 2 TV archive" },
  { name: "C-SPAN 3", networkId: "CSPAN3", years: "2001–2026", category: "Public affairs", blurb: "Public affairs and call-in program blocks.", query: "C-SPAN 3 TV archive" },
  { name: "CNBC", networkId: "CNBC", years: "1989–2026", category: "Business", blurb: "Business news and market hours.", query: "CNBC TV archive" },
  { name: "CNN", networkId: "CNN", years: "1980–2026", category: "News", blurb: "Cable news and headline roundups.", query: "CNN TV archive" },
  { name: "Comedy Central", networkId: "CC", years: "1991–2026", category: "Comedy", blurb: "Stand-up, sketch, satire, and comedy marathons.", query: "Comedy Central TV archive" },
  { name: "Court TV", networkId: "COURT", years: "1991–2026", category: "Legal", blurb: "Courtroom and civil-justice coverage.", query: "Court TV archive" },
  { name: "Crime + Investigation", networkId: "CI", years: "2003–2026", category: "True crime", blurb: "Investigative documentaries and unsolved cases.", query: "Crime Investigation TV archive" },
  { name: "Discovery", networkId: "DISC", years: "1985–2026", category: "Science", blurb: "Science, technology, and documentary blocks.", query: "Discovery Channel TV archive" },
  { name: "Disney Channel", networkId: "DISNEY", years: "1983–2026", category: "Kids", blurb: "Family programming and animation classics.", query: "Disney Channel TV archive" },
  { name: "E!", networkId: "E!", years: "1991–2026", category: "Entertainment", blurb: "Entertainment news and celebrity-driven programming.", query: "E! TV archive" },
  { name: "ESPN", networkId: "ESPN", years: "1979–2026", category: "Sports", blurb: "Sports news, highlight packages, and event coverage.", query: "ESPN TV archive" },
  { name: "ESPN2", networkId: "ESPN2", years: "1993–2026", category: "Sports", blurb: "Secondary sports and alternative live coverage.", query: "ESPN2 TV archive" },
  { name: "ESPN Classic", networkId: "ESPNC", years: "1997–2026", category: "Sports", blurb: "Classic games and sports documentary marathons.", query: "ESPN Classic TV archive" },
  { name: "Food Network", networkId: "FN", years: "1993–2026", category: "Lifestyle", blurb: "Cooking shows and culinary host marathons.", query: "Food Network TV archive" },
  { name: "Fox Business", networkId: "FBN", years: "2007–2026", category: "Business", blurb: "Market coverage and economic analysis.", query: "Fox Business TV archive" },
  { name: "Fox News", networkId: "FNC", years: "1996–2026", category: "News", blurb: "National and global news programming blocks.", query: "Fox News TV archive" },
  { name: "FX", networkId: "FX", years: "1994–2026", category: "Drama", blurb: "Dramas, films, and edgy entertainment.", query: "FX TV archive" },
  { name: "FXX", networkId: "FXX", years: "2013–2026", category: "Comedy", blurb: "Comedy reruns and cult favorites.", query: "FXX TV archive" },
  { name: "Hallmark Channel", networkId: "HALL", years: "2001–2026", category: "Family", blurb: "Holiday films and feel-good family stories.", query: "Hallmark Channel TV archive" },
  { name: "Hallmark Movies & Mysteries", networkId: "HMM", years: "2001–2026", category: "Movies", blurb: "Mystery and family-friendly movie blocks.", query: "Hallmark Movies and Mysteries TV archive" },
  { name: "HBO", networkId: "HBO", years: "1975–2026", category: "Movies", blurb: "Premium storytelling and feature films.", query: "HBO TV archive" },
  { name: "HGTV", networkId: "HGTV", years: "1994–2026", category: "Home", blurb: "Home design, renovation, and property shows.", query: "HGTV TV archive" },
  { name: "History", networkId: "HISTORY", years: "1995–2026", category: "History", blurb: "Military, civilization, and documentary blocks.", query: "History Channel TV archive" },
  { name: "IFC", networkId: "IFC", years: "1994–2026", category: "Indie", blurb: "Independent films, comedy, and cult titles.", query: "IFC TV archive" },
  { name: "Investigation Discovery", networkId: "ID", years: "1996–2026", category: "True crime", blurb: "Investigation-heavy documentary marathons.", query: "Investigation Discovery TV archive" },
  { name: "Lifetime", networkId: "LIFE", years: "1984–2026", category: "Drama", blurb: "Lifetime movies and social-drama storytelling.", query: "Lifetime TV archive" },
  { name: "Lifetime Movie Network", networkId: "LMN", years: "1996–2026", category: "Movies", blurb: "Movies for women and emotional drama blocks.", query: "Lifetime Movie Network TV archive" },
  { name: "MTV", networkId: "MTV", years: "1981–2026", category: "Music", blurb: "Music video hits and youth culture programming.", query: "MTV TV archive" },
  { name: "MSNBC", networkId: "MSNBC", years: "1996–2026", category: "News", blurb: "Cable news and political analysis.", query: "MSNBC TV archive" },
  { name: "NBC", networkId: "NBC", years: "1980–2026", category: "Broadcast", blurb: "Broadcast-era reruns and entertainment blocks.", query: "NBC TV archive" },
  { name: "Nickelodeon", networkId: "NICK", years: "1979–2026", category: "Kids", blurb: "Cartoon and children’s programming classics.", query: "Nickelodeon TV archive" },
  { name: "Nick at Nite", networkId: "NAN", years: "1985–2026", category: "Comedy", blurb: "Classic sitcom marathons for late-night viewing.", query: "Nick at Nite TV archive" },
  { name: "OWN", networkId: "OWN", years: "2009–2026", category: "Lifestyle", blurb: "Lifestyle and aspiration-focused programming.", query: "OWN TV archive" },
  { name: "PBS", networkId: "PBS", years: "1970–2026", category: "Public", blurb: "Documentary, arts, and educational programming.", query: "PBS TV archive" },
  { name: "PBS Kids", networkId: "PBSK", years: "1999–2026", category: "Kids", blurb: "Education-first children’s program blocks.", query: "PBS Kids TV archive" },
  { name: "Paramount Network", networkId: "PARAMOUNT", years: "2018–2026", category: "Entertainment", blurb: "Movies and pop-culture entertainment.", query: "Paramount Network TV archive" },
  { name: "Showtime", networkId: "SHO", years: "1976–2026", category: "Premium", blurb: "Premium drama and cinematic storytelling.", query: "Showtime TV archive" },
  { name: "Spike", networkId: "SPIKE", years: "1987–2026", category: "Action", blurb: "Action, sports, and male-oriented programming.", query: "Spike TV archive" },
  { name: "Starz", networkId: "STARZ", years: "1994–2026", category: "Movies", blurb: "Movie premium programming and event blocks.", query: "Starz TV archive" },
  { name: "SundanceTV", networkId: "SUNDANCE", years: "1996–2026", category: "Indie", blurb: "Independent film and art-house programming.", query: "Sundance TV archive" },
  { name: "Syfy", networkId: "SYFY", years: "1992–2026", category: "Sci-fi", blurb: "Genre features and cult-classic blocks.", query: "Syfy TV archive" },
  { name: "TBS", networkId: "TBS", years: "1976–2026", category: "Comedy", blurb: "Comedy reruns, sitcom marathons, and sports.", query: "TBS TV archive" },
  { name: "TLC", networkId: "TLC", years: "1972–2026", category: "Lifestyle", blurb: "Lifestyle, health, and home-oriented content.", query: "TLC TV archive" },
  { name: "TNT", networkId: "TNT", years: "1988–2026", category: "Movies", blurb: "Feature films and dramatic rerun blocks.", query: "TNT TV archive" },
  { name: "Travel Channel", networkId: "TRAVEL", years: "1987–2026", category: "Travel", blurb: "Destination, culture, and culinary travel stories.", query: "Travel Channel TV archive" },
  { name: "truTV", networkId: "TRUTV", years: "1998–2026", category: "Reality", blurb: "Courtroom reality and iconic comedy stunts.", query: "truTV TV archive" },
  { name: "TV Land", networkId: "TVL", years: "1996–2026", category: "Classic TV", blurb: "Classic sitcom reruns and nostalgia programming.", query: "TV Land TV archive" },
  { name: "USA Network", networkId: "USA", years: "1977–2026", category: "Entertainment", blurb: "Action, dramas, and accessible entertainment blocks.", query: "USA Network TV archive" },
  { name: "VH1", networkId: "VH1", years: "1985–2026", category: "Music", blurb: "Music video, pop culture, and celebrity features.", query: "VH1 TV archive" },
  { name: "WE tv", networkId: "WEtv", years: "2007–2026", category: "Lifestyle", blurb: "Real-life and lifestyle observation programming.", query: "WE tv TV archive" },
  { name: "The Weather Channel", networkId: "TWC", years: "1982–2026", category: "Weather", blurb: "Forecasting and severe-weather coverage.", query: "The Weather Channel TV archive" },
  { name: "WWE Network", networkId: "WWE", years: "2014–2026", category: "Sports", blurb: "Wrestling showcase and event programming blocks.", query: "WWE Network TV archive" },
  { name: "GSN", networkId: "GSN", years: "1994–2026", category: "Game", blurb: "Game-show replays and competition blocks.", query: "Game Show Network TV archive" },
  { name: "Oxygen", networkId: "OXY", years: "1998–2026", category: "Lifestyle", blurb: "Crime, reality, and women-centered programming.", query: "Oxygen TV archive" },
  { name: "Cinemax", networkId: "CMAX", years: "1980–2026", category: "Movies", blurb: "Premium films and late-night movie blocks.", query: "Cinemax TV archive" },
  { name: "HBO 2", networkId: "HBO2", years: "1991–2026", category: "Movies", blurb: "Second-channel movie and original entertainment blocks.", query: "HBO 2 TV archive" },
  { name: "Max", networkId: "MAX", years: "1991–2026", category: "Movies", blurb: "Premium movies and modern cinema blocks.", query: "Max TV archive" },
  { name: "Epix", networkId: "EPIX", years: "2009–2026", category: "Movies", blurb: "Cinema and premium feature films.", query: "Epix TV archive" },
  { name: "Freeform", networkId: "FREE", years: "1979–2026", category: "Young adults", blurb: "Youth-oriented programming and storytelling blocks.", query: "Freeform TV archive" },
  { name: "National Geographic", networkId: "NGC", years: "1985–2026", category: "Documentary", blurb: "Expedition and nature documentary marathons.", query: "National Geographic TV archive" },
  { name: "Nat Geo Wild", networkId: "NGW", years: "2006–2026", category: "Wildlife", blurb: "Animal behavior and conservation storytelling.", query: "Nat Geo Wild TV archive" },
  { name: "The CW", networkId: "CW", years: "2006–2026", category: "Broadcast", blurb: "Network drama, teen sitcoms, and event programming.", query: "The CW TV archive" },
  { name: "The Movie Channel", networkId: "TMC", years: "1979–2026", category: "Movies", blurb: "Classic feature films and curated cinematic blocks.", query: "The Movie Channel TV archive" },
  { name: "Logo", networkId: "LOGO", years: "2005–2026", category: "LGBTQ+", blurb: "Queer culture, film, and entertainment blocks.", query: "Logo TV archive" },
  { name: "Fuse", networkId: "FUSE", years: "1994–2026", category: "Music", blurb: "Music culture and alternative entertainment.", query: "Fuse TV archive" },
  { name: "Univision", networkId: "UNI", years: "1986–2026", category: "Spanish", blurb: "Spanish-language entertainment and news blocks.", query: "Univision TV archive" },
  { name: "Telemundo", networkId: "TEL", years: "1984–2026", category: "Spanish", blurb: "Spanish-language drama and entertainment blocks.", query: "Telemundo TV archive" },
  { name: "Galavisión", networkId: "GALA", years: "1981–2026", category: "Spanish", blurb: "Spanish-language programming and classic network blocks.", query: "Galavision TV archive" },
  { name: "TeleXitos", networkId: "TX", years: "2012–2026", category: "Spanish", blurb: "Short-form entertainment and classic telenovela programming.", query: "TeleXitos TV archive" },
  { name: "Nick Jr.", networkId: "NJR", years: "1988–2026", category: "Kids", blurb: "Preschool and early-learning blocks.", query: "Nick Jr TV archive" },
  { name: "Disney Junior", networkId: "DJR", years: "2011–2026", category: "Kids", blurb: "Preschool storytelling and animated programming.", query: "Disney Junior TV archive" },
  { name: "Cartoon Network", networkId: "CN", years: "1992–2026", category: "Animation", blurb: "Animated classics and cartoon marathons.", query: "Cartoon Network TV archive" },
  { name: "Boomerang", networkId: "BMG", years: "1992–2026", category: "Animation", blurb: "Classic cartoon reruns and Saturday-morning nostalgia.", query: "Boomerang TV archive" },
  { name: "Adult Swim", networkId: "AS", years: "2001–2026", category: "Animation", blurb: "Late-night animation and cult programming.", query: "Adult Swim TV archive" },
  { name: "Discovery Family", networkId: "DFAM", years: "2010–2026", category: "Family", blurb: "Adventure, animals, and family documentary programming.", query: "Discovery Family TV archive" },
  { name: "BET Her", networkId: "BETH", years: "2019–2026", category: "Lifestyle", blurb: "Women-forward lifestyle and entertainment blocks.", query: "BET Her TV archive" },
  { name: "BET Soul", networkId: "BTS", years: "2017–2026", category: "Music", blurb: "Soul, R&B, and music-video scheduling.", query: "BET Soul TV archive" },
  { name: "Great American Country", networkId: "GAC", years: "2007–2026", category: "Lifestyle", blurb: "Country music and rural-lifestyle programming.", query: "Great American Country TV archive" },
  { name: "RFD-TV", networkId: "RFD", years: "1996–2026", category: "Rural", blurb: "Farm, country, and lifestyle-heavy programming.", query: "RFD TV archive" },
  { name: "World Fishing Network", networkId: "WFN", years: "2002–2026", category: "Outdoors", blurb: "Fishing, outdoors, and travel features.", query: "World Fishing Network TV archive" },
  { name: "The Outdoor Channel", networkId: "OUTD", years: "1994–2026", category: "Outdoors", blurb: "Hunting, fishing, and outdoors programming.", query: "Outdoor Channel TV archive" },
  { name: "DIY Network", networkId: "DIY", years: "1999–2026", category: "Home", blurb: "Home improvement and practical build blocks.", query: "DIY Network TV archive" },
  { name: "Home & Garden TV", networkId: "H&G", years: "1979–2026", category: "Home", blurb: "Garden, home, and design inspiration blocks.", query: "Home and Garden TV archive" },
  { name: "QVC", networkId: "QVC", years: "1986–2026", category: "Retail", blurb: "Shopping and lifestyle programming blocks.", query: "QVC TV archive" },
  { name: "HSN", networkId: "HSN", years: "1982–2026", category: "Retail", blurb: "Home-shopping and lifestyle program blocks.", query: "HSN TV archive" },
  { name: "Golf Channel", networkId: "GOLF", years: "1995–2026", category: "Sports", blurb: "Golf instruction, tournaments, and analysis.", query: "Golf Channel TV archive" },
  { name: "Sportsman Channel", networkId: "SPORTSMAN", years: "2003–2026", category: "Outdoors", blurb: "Hunting, fishing, and outdoor sports coverage.", query: "Sportsman Channel TV archive" },
  { name: "Black News Channel", networkId: "BNC", years: "2020–2026", category: "News", blurb: "Black-oriented news and public-affairs broadcasts.", query: "Black News Channel TV archive" },
  { name: "Ion Television", networkId: "ION", years: "1998–2026", category: "General", blurb: "Classic dramas, family specials, and network reruns.", query: "ION Television TV archive" },
  { name: "Ion Plus", networkId: "IONP", years: "2012–2026", category: "General", blurb: "Additional game, drama, and lifestyle blocks.", query: "Ion Plus TV archive" },
  { name: "Bounce", networkId: "BOUNCE", years: "2011–2026", category: "Entertainment", blurb: "Movies, live sports, and Black entertainment staples.", query: "Bounce TV archive" },
  { name: "Hallmark Drama", networkId: "HLD", years: "2017–2026", category: "Drama", blurb: "Dramas, romance, and character-driven storytelling.", query: "Hallmark Drama TV archive" },
  { name: "ABC", networkId: "ABC", years: "1980–2026", category: "Broadcast", blurb: "Broadcast-day archive reruns and entertainment blocks.", query: "ABC TV archive" },
  { name: "CBS", networkId: "CBS", years: "1980–2026", category: "Broadcast", blurb: "Long-form episode blocks and prime-time nostalgia.", query: "CBS TV archive" },
  { name: "Fox Broadcasting", networkId: "FOX", years: "1986–2026", category: "Broadcast", blurb: "Independent station-style programming and network reruns.", query: "Fox Broadcasting TV archive" },
  { name: "WB", networkId: "WB", years: "1988–2026", category: "Broadcast", blurb: "Teen dramas, sitcom reruns, and classic nights.", query: "The WB TV archive" },
  { name: "UPN", networkId: "UPN", years: "1995–2026", category: "Broadcast", blurb: "Young-adult programming and evening repeats.", query: "UPN TV archive" },
  { name: "The Hub", networkId: "HUB", years: "2010–2026", category: "Kids", blurb: "Preschool and family-centered educational blocks.", query: "The Hub TV archive" },
  { name: "Antenna TV", networkId: "ANT", years: "2011–2026", category: "Classic TV", blurb: "Classic series and legacy local-channel archival blocks.", query: "Antenna TV archive" },
  { name: "MeTV", networkId: "METV", years: "2003–2026", category: "Classic TV", blurb: "Classic sitcoms, dramas, and family nostalgia.", query: "MeTV TV archive" },
  { name: "Cozi TV", networkId: "COZI", years: "2006–2026", category: "Classic TV", blurb: "Classic television and heritage network programming.", query: "Cozi TV archive" },
  { name: "MAVTV", networkId: "MAV", years: "2004–2026", category: "Sports", blurb: "Motorsports and racing-feature blocks.", query: "MAVTV TV archive" },
  { name: "Newsy", networkId: "NEWSY", years: "2014–2026", category: "News", blurb: "News summary and documentary-style coverage blocks.", query: "Newsy TV archive" },
  { name: "Newsmax", networkId: "NMAX", years: "2014–2026", category: "News", blurb: "Public-affairs and current-events programming.", query: "Newsmax TV archive" },
  { name: "Cheddar", networkId: "CHDR", years: "2017–2026", category: "Business", blurb: "Financial news and market-driven programming.", query: "Cheddar TV archive" },
  { name: "AWE", networkId: "AWE", years: "2018–2026", category: "Lifestyle", blurb: "Family and maker-oriented stories and shows.", query: "AWE TV archive" },
  { name: "Scripps News", networkId: "SPN", years: "2021–2026", category: "News", blurb: "News routines and state-of-the-day coverage blocks.", query: "Scripps News TV archive" },
  { name: "Stadium", networkId: "STAD", years: "2017–2026", category: "Sports", blurb: "Live sports and highlight-driven rounds.", query: "Stadium TV archive" },
  { name: "Tennis Channel", networkId: "TENNIS", years: "2003–2026", category: "Sports", blurb: "Tennis events and instructional content blocks.", query: "Tennis Channel TV archive" },
  { name: "NFL Network", networkId: "NFL", years: "2003–2026", category: "Sports", blurb: "Games, interviews, and football programming blocks.", query: "NFL Network TV archive" },
  { name: "MLB Network", networkId: "MLB", years: "2009–2026", category: "Sports", blurb: "Baseball coverage and archive-driven game recaps.", query: "MLB Network TV archive" },
  { name: "NHL Network", networkId: "NHL", years: "2007–2026", category: "Sports", blurb: "Hockey highlights and archival coverage blocks.", query: "NHL Network TV archive" },
  { name: "NBA TV", networkId: "NBA", years: "1999–2026", category: "Sports", blurb: "Basketball action and recaps across the day.", query: "NBA TV archive" },
  { name: "BYUtv", networkId: "BYU", years: "2000–2026", category: "Family", blurb: "Family and faith-oriented programming blocks.", query: "BYUtv TV archive" }
];

const channels = channelSeed.map((channel, index) => ({
  id: `${channel.name.toLowerCase().replace(/[^a-z0-9]+/g, "-")}-${index}`,
  ...channel,
  source: buildArchiveUrl(channel.query)
}));

const selectedChannel = { id: channels[0].id };

function buildArchiveUrl(query) {
  return `https://archive.org/search?query=${encodeURIComponent(query)}`;
}

function formatClock() {
  const now = new Date();
  const locale = new Intl.DateTimeFormat("en-US", {
    timeZone: "America/New_York",
    hour: "numeric",
    minute: "2-digit",
    second: "2-digit",
    hour12: true
  });
  return `${locale.format(now)} ET`;
}

function buildSchedule(channel) {
  return defaultSchedule.map((slot) => ({
    ...slot,
    description:
      slot.label === "Overnight archive"
        ? `${channel.name} late-night archive loops and looped brand cues.`
        : slot.label === "Early-morning nostalgia"
          ? `${channel.name} lifestyle and broadcast-era warm-up programming.`
          : slot.label === "Daytime classics"
            ? `${channel.name} daytime continuity and classic rerun blocks.`
            : slot.label === "Afternoon lineup"
              ? `${channel.name} midday viewing and iconic feature programming.`
              : slot.label === "Prime-time block"
                ? `${channel.name} flagship entertainment and signature program block.`
                : `${channel.name} late-night wrap with marquee reruns and sign-off identity.`
  }));
}

function renderSelectedChannel() {
  const channel = channels.find((item) => item.id === selectedChannel.id) || channels[0];
  const scheduleContainer = document.getElementById("selectedChannelSchedule");
  const selectedChannelName = document.getElementById("selectedChannelName");
  const selectedChannelBlurb = document.getElementById("selectedChannelBlurb");
  const sourceLink = document.getElementById("sourceLink");
  const activeChannelId = document.getElementById("activeChannelId");

  const programBlocks = buildSchedule(channel);
  scheduleContainer.innerHTML = programBlocks
    .map(
      (slot) => `
        <article class="time-block">
          <strong>${slot.start}–${slot.end}</strong>
          <span>${slot.label}</span>
          <p>${slot.description}</p>
        </article>
      `
    )
    .join("");

  selectedChannelName.textContent = channel.name;
  selectedChannelBlurb.textContent = channel.blurb;
  activeChannelId.textContent = channel.networkId;
  sourceLink.href = channel.source;
  sourceLink.title = `${channel.name} archival source`;
}

function renderChannelGrid() {
  const grid = document.getElementById("channelGrid");

  grid.innerHTML = channels
    .map(
      (channel) => `
        <article class="channel-card ${channel.id === selectedChannel.id ? "selected" : ""}" data-id="${channel.id}">
          <div class="channel-header">
            <span class="channel-badge">${channel.networkId}</span>
            <span class="channel-years">${channel.years}</span>
          </div>

          <h3>${channel.name}</h3>
          <p class="meta">${channel.blurb}</p>

          <div class="channel-meta">
            <span>${channel.category}</span>
          </div>

          <ul class="schedule-list">
            ${defaultSchedule
              .slice(0, 3)
              .map(
                (slot) => `
                  <li>
                    <span>${slot.start}–${slot.end}</span>
                    <strong>${slot.label}</strong>
                  </li>
                `
              )
              .join("")}
          </ul>

          <a href="${channel.source}" target="_blank" rel="noreferrer">Archive source</a>
        </article>
      `
    )
    .join("");

  grid.querySelectorAll(".channel-card").forEach((card) => {
    card.addEventListener("click", () => {
      selectedChannel.id = card.dataset.id;
      renderChannelGrid();
      renderSelectedChannel();
    });
  });
}

function init() {
  const clock = document.getElementById("liveClock");
  const tick = () => {
    clock.textContent = formatClock();
  };

  tick();
  setInterval(tick, 1000);

  renderSelectedChannel();
  renderChannelGrid();
}

init();
