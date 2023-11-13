const eventDuration = 2;
const calendar = CalendarApp.getCalendarById("bfd15a133d46eeaabf81525b487ec374d64f82fe394261edd7a3a3f91b031c4b@group.calendar.google.com")

function createEvent() {
  const ws = SpreadsheetApp.getActiveSpreadsheet(); 
  const ss = ws.getActiveSheet(); 
  for (var i = 2; i <= ss.getLastRow(); i++) {
    const created = ss.getRange(i,4).getValue();
    if(created != "Event Created"){
    const eventName = ss.getRange(i,1).getValue();
    const author = ss.getRange(i,3).getValue();
    const date = ss.getRange(i,2).getValue();
    var startingDate = new Date(date);
    
    var endingDate = new Date(date);
    endingDate.setHours(startingDate.getHours() + eventDuration);

  calendar.createEvent(eventName, startingDate, endingDate,);
  ss.getRange(i,4).setValue("Event Created")
    }
  }
}

function menuCreation() {
  SpreadsheetApp.getUi().createMenu("Auto Scheduler Commands").addItem("📅Generate All Events", "createEvent").addToUi();
}
